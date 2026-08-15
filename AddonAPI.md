## Introduction

`StarScriptAddonAPI` is a free, unrestricted, developer-facing API for registering custom
mechanics, conditions, targeters, triggers, and placeholders into StarScript from **another
plugin** — distinct from [Extension Scripting](Skills-extensions) (a Premium, end-user
scripting feature for `.java`/`.js` files dropped into a script pack). If you're writing a
Bukkit/Paper plugin and want it to add its own StarScript mechanics/conditions/etc., this page
is for you. If you're writing a StarScript *script* and want to add a custom mechanic inline,
see [Extension Scripting](Skills-extensions) instead.

Everything registered through this API behaves exactly like a built-in StarScript mechanic or a
built-in MythicMobs one — usable from any skill line, mob config, or script, by anyone on the
server, with no awareness that it came from a third-party addon.

There are two ways to use it:

- **As an ordinary Bukkit plugin** — your own jar in `plugins/`, your own `plugin.yml` with
  `softdepend: [StarScript]`, calling `StarScriptAddonAPI.get()` from your own `onEnable()`.
- **As a StarScript-managed addon** — a smaller jar (no `plugin.yml`, no classloader/lifecycle
  of its own) dropped into `plugins/StarScript/addons/`, which StarScript scans and loads itself.

Both paths register into the exact same registries — pick whichever fits your project. The
Bukkit-plugin path is the better default if you're already shipping a plugin; the
StarScript-managed path is a lighter option for something that only exists to add StarScript
mechanics and nothing else.

## Compiling against it

Add the thin addon-API jar as a `compileOnly` dependency — it contains only interfaces, no
implementation, and is small (a few KB):

```kotlin
dependencies {
    compileOnly(files("libs/StarScript-Premium-<version>-api.jar"))
}
```

If you plan to register a custom [trigger](#triggers), you additionally need StarScript's full
plugin jar on your compile classpath (not just the api jar) for `TriggerDefinition`/
`EventContext`, plus MythicMobs' own API jar (`io.lumine:Mythic-Dist`) for `MythicLineConfig` —
see [Triggers](#triggers) below.

## As a Bukkit plugin

`plugin.yml`:
```yaml
name: MyAddon
version: 1.0.0
main: com.example.myaddon.MyAddon
softdepend: [StarScript]
```

```java
public final class MyAddon extends JavaPlugin {
    @Override
    public void onEnable() {
        if (!Bukkit.getPluginManager().isPluginEnabled("StarScript")) {
            return; // StarScript not installed - nothing to register into
        }
        StarScriptAddonAPI api = StarScriptAddonAPI.get();
        api.mechanics().register("mycoolmechanic", ctx -> {
            ctx.caster().sendMessage("Hello from my addon!");
            return AddonSkillOutcome.SUCCESS;
        });
    }
}
```

`StarScriptAddonAPI.get()` throws `IllegalStateException` if StarScript isn't installed/enabled
— always guard with `isPluginEnabled("StarScript")` first, exactly like any other soft
dependency.

## As a StarScript-managed addon

No `plugin.yml`, no `JavaPlugin` subclass — instead, extend `StarScriptAddon` and provide an
`addon.yml` at your jar's root:

```yaml
name: MyAddon
version: 1.0.0
main: com.example.myaddon.MyAddon
```

```java
public final class MyAddon extends StarScriptAddon {
    @Override
    public void onEnable() {
        getApi().mechanics().register("mycoolmechanic", ctx -> {
            ctx.caster().sendMessage("Hello from my addon!");
            return AddonSkillOutcome.SUCCESS;
        });
    }

    @Override
    public void onDisable() {
        // optional cleanup
    }
}
```

Drop the built jar into `plugins/StarScript/addons/` (created automatically on first run) and
restart the server. `getContext()` (or the `getApi()`/`getName()`/`getVersion()` shorthands) is
only valid once `onLoad()`/`onEnable()` has been called — StarScript injects it right before.

`getContext()` also exposes `plugin()` (StarScript's own `JavaPlugin`, for scheduling/logging),
`logger()` (prefixed with your addon's name), `dataFolder()`
(`plugins/StarScript/addons/<name>/`, created automatically), and `registerListener(Listener)`.

**Caveat**: each addon gets its own child classloader (parent = StarScript's), independent of
Bukkit's normal plugin classloader graph. If your addon needs classes from another plugin (e.g.
Vault), that plugin must already be on the classpath your child classloader can see — a missing
dependency logs a clear warning (`missing dependency: ...`) instead of crashing the server, but
the addon simply won't load. If you need tight integration with another plugin's API, the
Bukkit-plugin path above is usually simpler.

## Mechanics

```java
api.mechanics().register("mycoolmechanic", ctx -> {
    // ctx.caster(), ctx.targetEntity(), ctx.targetLocation(), ctx.origin()
    // ctx.config().string("key", "default"), .integer(...), .number(...), .bool(...)
    // ctx.resolve("<caster.name> did a thing") - resolves MythicMobs placeholders
    // ctx.variable("name"), ctx.variable("name", value) - skill-line variables
    return AddonSkillOutcome.SUCCESS; // or ERROR / INVALID_TARGET / INVALID_CONFIG / CONDITION_FAILED
});
```

Usable from any skill line as `mycoolmechanic{key=value}`. `register(name, aliases, handler)`
also accepts a `List<String>` of additional names. Override `AddonMechanicHandler.init(config)`
to validate/parse config once per skill line, before any `cast`.

## Conditions

```java
api.conditions().register("mycoolcondition", ctx -> {
    // ctx.entity(), ctx.location(), ctx.caster(), ctx.config(), ctx.resolve(template)
    return true;
});
```

Usable as `?mycoolcondition{key=value}` inline, or in a `Conditions:`/`TargetConditions:` block.

## Targeters

```java
api.targeters().register("mycooltargeter", ctx -> {
    // ctx.caster(), ctx.origin(), ctx.config(), ctx.resolve(template)
    return List.of(ctx.caster());
});
```

Usable as `@mycooltargeter{key=value}`.

## Triggers

Trigger registration reuses StarScript's real `TriggerDefinition`/`EventContext` types directly
rather than a separate addon-facing abstraction — both are already public and safe to build
against. This means you need StarScript's **full** plugin jar (not just the api jar) plus
MythicMobs' own API jar on your compile classpath:

```kotlin
dependencies {
    compileOnly(files("libs/StarScript-Premium-<version>.jar"))
    compileOnly("io.lumine:Mythic-Dist:5.12.0") { isTransitive = false }
}
```

```java
api.triggers().register(new TriggerDefinition("mycooltrigger", PlayerJoinEvent.class, (event, config) -> {
    PlayerJoinEvent e = (PlayerJoinEvent) event;
    return EventContext.forPlayer(e.getPlayer());
}));
```

Usable as `~onMycoolTrigger{config}` in a script's `Skills:` list. See
[Triggers](Skills-Triggers) for the general `~onX` token model this plugs into.

## Placeholders

```java
// Static/template-style, resolved once:
api.placeholders().register(this, "greeting", "Hello, <caster.name>!");

// Dynamic, re-evaluated on every resolution:
api.placeholders().register(this, "playercount", ctx -> String.valueOf(Bukkit.getOnlinePlayers().size()));
```

(For the `StarScriptAddon` path, pass `getContext().plugin()` instead of `this` as the owner.)

Registered under `<addon.pluginname.name>` in MythicMobs placeholder strings, and mirrored to
PlaceholderAPI as `%starscript_addon_pluginname_name%` if PlaceholderAPI is installed. The
owning plugin's name namespaces every placeholder, so two addons can each register a `greeting`
placeholder without colliding.

## Unregistering

Every registry has an `unregister(name)` (placeholders: `unregister(owner, name)`). This only
stops **future** matches — MythicMobs has no mechanism to hot-unbind a skill line that already
resolved to your mechanic/condition/targeter instance, so lines already loaded keep behaving per
their already-bound instance. Call `unregister` from your `onDisable()` mainly to avoid stale
matches if your plugin/addon reloads, not as a live on/off switch.

## See Also

- [Extension Scripting](Skills-extensions) — the Premium, script-file-based equivalent for
  script authors (not plugin developers).
- [Mechanics](Skills-Mechanics) / [Conditions](Skills-Conditions) /
  [Targeters](Skills-Targeters) / [Triggers](Skills-Triggers) — StarScript's own built-in
  additions, registered the same way internally.
