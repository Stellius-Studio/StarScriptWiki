# Extension Scripting (Premium)

StarScript lets script authors define their **own** mechanics, conditions, targeters, and
placeholders, and hook into other plugins, without waiting for those to be added to the plugin
itself. There are four ways to do this, all controlled by the same feature gate:

1. **Java source files**, compiled on the server at load time.
2. **Precompiled `.class`/`.jar` drops** - already-built Java, no compiler needed on the server.
3. **JavaScript files**, run by an embedded GraalJS engine.
4. **Reflection one-liners** directly inside ordinary YAML scripts (`javainvoke`, `javanew`,
   `javafield`, `javacheck`, `jseval`).

This is a **Premium** feature. On Free builds, extension bundles are still scanned (so the log
can tell you how many were found) but nothing is registered, and the reflection mechanics/
condition all no-op — each prints its own one-time upgrade banner pointing at the upgrade page
(the bundle-scan banner at load, the reflection one on first use). It can also be turned off
independently of edition with `Extensions.Enabled: false` in `config.yml` (this only affects
extension bundles, not the always-registered reflection mechanics).

## Where files go

```
plugins/StarScript/scripts/extensions/
  economy.yml            <- a manifest bundle
  PayMechanic.java        <- referenced by the manifest, compiled at load time
  weather.js
  QuickSmite.java          <- no manifest -> auto-loaded as its own zero-dependency bundle
  MyCompiled.class          <- precompiled, no manifest needed
  mystuff.jar               <- precompiled, no manifest needed
```

Any `.java`, `.js`, `.class`, or `.jar` file that isn't referenced by a manifest is picked up
automatically as its own bundle with no dependencies. Files starting with `-` are ignored (same
convention as the rest of `scripts/`).

The same `extensions/` folder is also searched inside every MythicMobs pack's `Scripts/`
subfolder — `plugins/MythicMobs/packs/<name>/Scripts/extensions/` — so an addon pack can ship its
own extension bundle alongside its `Mobs:`/`Skills:` content. See [Pack Scripts](Skills-PackScripts).

## Manifests

A manifest is a normal YAML file. Each top-level key names a **bundle**:

```yaml
EconomyPack:
  Depends:
  - Vault                 # hard dependency: bundle is skipped (with a clear log line) if missing
  - Essentials optional    # optional: loads anyway if missing, your code should check for it

  Libraries:
  - org.apache.commons:commons-lang3:3.17.0   # group:artifact:version, downloaded from Maven Central

  Java:
  - PayMechanic.java       # compiled at load time

  Classes:
  - mystuff.jar             # precompiled - a .jar or loose .class file, no compiler needed

  Scripts:
  - weather.js
```

Notes:

- **Names of mechanics/conditions/targeters are never in the manifest** - they come from your
  code (`@ScriptedExtension(name = "...")` in Java, `registerMechanic("...", ...)` in JS). The
  manifest only wires up dependencies and points at files.
- `Libraries:` entries are downloaded once into `plugins/StarScript/libs/` (the same folder the
  database drivers use) and shared across bundles that name the same coordinate. There's no
  transitive resolution - if a library needs other jars, list them too.
- `Depends:` plugins are also added to the Java compiler's classpath automatically, so your
  `.java` sources can reference their API directly.

## Writing a Java extension

```java
import com.stelliusstudio.starscript.api.extension.*;

@ScriptedExtension(name = "smite", type = ExtensionType.MECHANIC)
public class SmiteMechanic implements MechanicHandler {
    @Override
    public SkillOutcome cast(MechanicContext ctx) {
        var location = ctx.targetLocation();
        if (location == null) return SkillOutcome.INVALID_TARGET;
        location.getWorld().strikeLightningEffect(location);
        return SkillOutcome.SUCCESS;
    }
}
```

- The class needs a public no-arg constructor and must implement the handler interface matching
  its `type()`: `MechanicHandler`, `ConditionHandler`, `TargeterHandler`, or `PlaceholderHandler`.
- One instance is created **per skill line** that uses it (same as MythicMobs' own mechanics), so
  `init(LineConfig)` (optional, called once at load) is the place to parse config that doesn't
  change per-cast. (`PlaceholderHandler` has no `init` - a placeholder isn't tied to a skill line;
  see below.)
- `MechanicContext`/`ConditionContext`/`TargeterContext` expose `caster()`, `targetEntity()`,
  `targetLocation()`, `origin()`, `config()` (read skill-line parameters), `resolve(String)`
  (MythicMobs placeholder resolution), and `variable(name)`/`variable(name, value)` (skill
  variables) - all in plain Bukkit types, no MythicMobs API required. `rawMetadata()` is an escape
  hatch into the underlying `SkillMetadata` if you need it.
- Compiling requires a full JDK on the server (the `jdk.compiler` module). If the server is
  running a JRE or a jlinked runtime without it, `.java` sources are skipped with a clear log
  message; `.class`/`.jar`/`.js` extensions are unaffected.

## Dropping in precompiled classes

If you'd rather compile with your own toolchain (or the server doesn't have a JDK), build against
the `com.stelliusstudio.starscript.api.extension` package from the plugin jar and drop the
result in:

- a `.jar` - every class inside with `@ScriptedExtension` is registered;
- a loose `.class` file - same, just the one class.

No manifest is required for either.

## Writing a placeholder extension

Placeholders work a little differently from mechanics/conditions/targeters: MythicMobs has no
per-use load event for them, so instead of one instance per skill line, **one shared instance**
is registered eagerly under `<script.ext.NAME>` as soon as the bundle loads (and re-registered on
every `/mm reload`, same as the `Placeholders:` YAML block already is):

```java
import com.stelliusstudio.starscript.api.extension.*;

@ScriptedExtension(name = "serverTps", type = ExtensionType.PLACEHOLDER)
public class TpsPlaceholder implements PlaceholderHandler {
    @Override
    public String resolve(PlaceholderContext ctx) {
        return String.format("%.1f", Bukkit.getServer().getTPS()[0]);
    }
}
```

```
<script.ext.serverTps>
```

- `PlaceholderContext` exposes `viewer()` (the resolving `OfflinePlayer`, or `null`), `entity()`,
  and `location()` - simpler than `MechanicContext`/etc. since a placeholder isn't tied to an
  active skill cast.
- Also mirrored to PlaceholderAPI (if installed) as `%starscript_ext_NAME%`.
- Unlike the other three types, a placeholder handler is resolved on **whichever thread reads the
  placeholder** (not necessarily the main thread) - keep it fast and avoid blocking calls.

## Writing a JavaScript extension

```js
registerMechanic("clearsky", function(ctx) {
    var location = ctx.targetLocation();
    if (location === null) return "INVALID_TARGET";
    location.getWorld().setStorm(false);
    return "SUCCESS";
});

registerCondition("isstorming", function(ctx) {
    return ctx.location() !== null && ctx.location().getWorld().hasStorm();
});

registerPlaceholder("isstorming2", function(ctx) {
    return (ctx.location() !== null && ctx.location().getWorld().hasStorm()) ? "true" : "false";
});
```

- `registerMechanic`/`registerCondition`/`registerTargeter`/`registerPlaceholder` are global
  functions available in every script file; the callback receives the same
  `MechanicContext`/`ConditionContext`/`TargeterContext`/`PlaceholderContext` as Java extensions.
- Mechanic callbacks can return `"SUCCESS"`/`"ERROR"`/`"INVALID_TARGET"`/`"INVALID_CONFIG"`/
  `"CONDITION_FAILED"` (case-insensitive), or nothing/`true` for success and `false` for error.
  Condition callbacks use normal truthiness. Placeholder callbacks just return a string (or
  `null`/nothing to fall back to MythicMobs' undefined-value sentinel).
- `Java.type("some.Class")` (standard GraalJS) or the `importClass("some.Class")` shorthand
  works for calling into Bukkit, other plugins, or your `Libraries:` jars.
- The JavaScript engine (GraalJS) is downloaded on first use into `plugins/StarScript/libs/` -
  about a dozen jars, roughly 25-30MB - and is never bundled in the plugin jar itself.
- It runs in interpreter mode on a stock JDK (no special JVM flags needed), which is fine for
  skill logic but not for tight numeric loops - keep hot paths in Java if you need raw speed.
- Every script's callbacks always run on the main server thread, so it's safe to touch Bukkit API
  directly; a script that blocks will stall that tick, same as any other synchronous mechanic.

## Reflection one-liners

For quick one-off Java calls that don't justify a whole extension bundle, four mechanics
([javanew](Skills-Mechanics-javanew), [javainvoke](Skills-Mechanics-javainvoke),
[javafield](Skills-Mechanics-javafield), [jseval](Skills-Mechanics-jseval)) and one condition
([javacheck](Skills-Conditions-javacheck)) are available in **any** script — same **Premium**
gate as the rest of this page; on Free builds they log a one-time upgrade banner on first use and
no-op:

```yaml
MyScript:
  Imports:
  - org.bukkit.Bukkit
  - java.util.UUID as UID

  Skills:
  - javanew{class=java.util.Random;var=rng} ~onJoin
  - javainvoke{target=var.rng;method=nextInt;args=int:100;var=roll} ~onJoin
  - javainvoke{class=Bukkit;method=getPlayer;args=str:<trigger.name>;var=p} ~onJoin
  - javafield{class=java.lang.Integer;field=MAX_VALUE;var=max} ~onJoin
  - jseval{js="ctx.caster().setFireTicks(40)"} ~onDamaged

  Conditions:
  - javacheck{class=Bukkit;method=isHardcore;expect=false}
```

- `Imports:` lets you use a class's simple name (`Random`) instead of writing it out fully
  (`java.util.Random`) elsewhere in the file; fully-qualified names always work everywhere,
  imported or not. Imports are global across all scripts (not scoped per-file) since these
  mechanics only see the raw config line, not which script it came from - so pick distinctive
  aliases if two different classes would otherwise share a simple name.
- `javainvoke{class=...}` calls a **static** method; `javainvoke{target=caster|target|origin|var.NAME}`
  calls an **instance** method on the caster, the cast target, the cast origin, or a value
  previously stored in a skill variable via `var=`.
- `javanew{class=...;args=...;var=...}` constructs an object and stores it.
- `javafield{...;var=...}` reads a field; `javafield{...;value=...}` writes one.
- `javacheck{class=...;method=...|field=...;expect=...}` is a condition comparing a static
  method's return value (or a static field) against a literal (default `"true"`).
- `args=` is a comma-separated list (`\,` to escape a literal comma), each entry optionally
  prefixed `str:`/`int:`/`long:`/`double:`/`float:`/`bool:`, or `null` for a real null argument;
  unprefixed values are guessed as int, then double, then boolean, then left as a string.
- Overload resolution picks the most specific matching method (exact type match beats numeric
  widening beats boxing beats a lenient string/number conversion) - if a call is ambiguous or
  doesn't match anything, the log names every candidate signature it considered and suggests a
  fix.
- These mechanics never reach into MythicMobs' own internals or JDK-module-private code; if a
  member genuinely isn't accessible, the log says so rather than silently failing.

## Reload behavior

`/mm reload` fully reloads extensions along with everything else: bundles are re-discovered,
Java is recompiled, JS contexts are recreated, and stale in-flight skill lines fail safely with a
log message instead of running old code. Extension placeholders are re-registered the same way
`Placeholders:` YAML entries already are.


## See Also
- [Mechanics](Skills-Mechanics) — including [javanew](Skills-Mechanics-javanew)/[javainvoke](Skills-Mechanics-javainvoke)/[javafield](Skills-Mechanics-javafield)/[jseval](Skills-Mechanics-jseval).
- [Conditions](Skills-Conditions) — including [javacheck](Skills-Conditions-javacheck).
- [Placeholders](Skills-Placeholders) — `<script.ext.NAME>` and `%starscript_ext_NAME%`, backed by this page's `PlaceholderHandler`.
- [Scripts](Skills-Scripts) — how `Skills:`/`Conditions:` lines and `Placeholders:` fit into a script file.
- [Pack Scripts](Skills-PackScripts) — extension bundles are also discovered from
  `Scripts/extensions/` inside any MythicMobs pack, not just StarScript's own data folder.
