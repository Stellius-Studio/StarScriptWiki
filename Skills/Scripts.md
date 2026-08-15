## Introduction
StarScript scripts are YAML files, styled exactly like MythicMobs mob configs. Each top-level
key in a script file is a script name; each script becomes a real registered MythicMobs
`MetaSkill` internally, executed by MythicMobs' own skill engine — so every mechanic, condition,
and targeter MythicMobs (and any installed MythicMobs addon) provides is usable in a
StarScript's `Skills:` list alongside StarScript's own additions documented in this
wiki.

Script files live in `plugins/StarScript/scripts/`. They're also discovered inside MythicMobs
packs — see [Pack Scripts](Skills-PackScripts) — so a script/targeter/compound-trigger/
extension bundle can ship alongside a pack's `Mobs:`/`Skills:`/etc. content instead of StarScript's
own data folder.


## Basic structure
```yaml
MyScript:
  Skills:
  - message{m="<aqua>Hello, <trigger.name>!"} @trigger ~onJoin
  - heal{amount=5} @trigger ~onRespawn
```

- **`Skills:`** — a list of skill lines, exactly like a MythicMobs mob's `Skills:` section.
  Each line is `mechanic{config} ?condition{config} @targeter ~trigger{config}`.
- **Triggers** (`~onX`) determine WHEN a line fires — see [Triggers](Skills-Triggers) for the full catalog.
  Lines sharing the same trigger token fire together on that event. A line with NO trigger token
  runs on every script event this script is bound to.
- **Targeters** (`@target`, `@trigger`, `@self`, etc.) determine WHO/WHAT the line acts on — the
  full set of MythicMobs targeters is available, unchanged.
- **Conditions** (`?condition{config}`) gate whether a line fires — see [Conditions](Skills-Conditions) for
  StarScript's own additions on top of MythicMobs' built-in condition set.


## `Commands:` — script-defined commands
```yaml
MyScript:
  Commands:
  - name: vip
    permission: starscript.vip
    usage: "/vip <player>"
  Skills:
  - message{m="<gold>VIP command used by <trigger.name>!"} @trigger
```
Registers a real Bukkit command that executes this script's `Skills:` list when run.


## `Placeholders:` — script-defined placeholders
```yaml
MyScript:
  Placeholders:
    rank.display: "<gold><skill.var.rank></gold>"
```
Exposes `<script.rank.display>` (and `%starscript_rank_display%` via PlaceholderAPI) — see
[Placeholders](Skills-Placeholders).


## Skill variables
Any mechanic or trigger that exposes contextual data does so as a skill variable, readable via
`<skill.var.NAME>` in later lines of the same cast (e.g. `<skill.var.event-item>` set by many
triggers — see each trigger's page for its exposed variables — or `<skill.var.coins>` set by
[getstorage](Skills-Mechanics-getstorage)).


## Universal trigger token options
Every `~onX{...}` token accepts four options on top of its own config, since they're handled by
StarScript's event dispatch itself rather than the trigger:

| Option           | Description                                                          | Default |
|-------------------|------------------------------------------------------------------------|---------|
| `priority`         | Bukkit `EventPriority` to listen at: `LOWEST`, `LOW`, `NORMAL`, `HIGH`, `HIGHEST`, or `MONITOR` | `NORMAL` |
| `ignorecancelled`   | If `true`, skip firing when the underlying event is already cancelled     | `false` |
| `cancel`            | If `true`, cancel the underlying event once this line's condition passes  | `false` |
| `delay`             | Ticks to wait before running the skill (20 ticks = 1 second)              | `0` (run immediately) |

```yaml
Skills:
- damage{amount=0} @trigger ~onDamage{cause=FALL;cancel=true}
```

**Why this matters for events other plugins also listen to.** For a Bukkit event several plugins
react to — combat and interaction events are the common case — priority decides listening order,
and a plugin at a higher priority can cancel the event before yours sees it. MythicCrucible, for
example, registers its own damage/interact triggers at `HIGH`/`HIGHEST` and can cancel those
events (shield blocks, its own `DAMAGED` trigger). A `~onDamage`/`~onAttack`/`~onInteract` script
left at the default `NORMAL` priority with no `ignorecancelled=` set will simply not fire for
whatever Crucible already cancelled — which is normal Bukkit behavior, not a bug, but easy to
be surprised by if you don't set `priority=`/`ignorecancelled=` explicitly on a combat/interact
trigger you expect to run unconditionally.

**`delay=` — for events that fire before the player is fully ready.** `~onJoin` in particular
fires while the player's connection/session is still settling in; a `message{...}` line on it can
silently go nowhere even though the trigger dispatched correctly. Give it a tick or two:

```yaml
Skills:
- message{m="<green>Welcome to the server, <trigger.name>!"} @trigger ~onJoin{delay=20}
```

The delay only defers running the skill — it doesn't affect `cancel=`, which (correctly) always
happens synchronously in the event's own tick, before any delay. If the player disconnects during
the wait, the delayed skill is silently skipped rather than erroring on a stale entity.


## See Also
- [Triggers](Skills-Triggers) — the full trigger catalog (`~onX` tokens).
- [Mechanics](Skills-Mechanics) — StarScript's custom mechanics.
- [Conditions](Skills-Conditions) — StarScript's custom conditions.
- [Extension Scripting](Skills-extensions) — write your own mechanics/conditions/targeters in Java/JS, or call Java directly with `Imports:` (Premium).
- [Placeholders](Skills-Placeholders) — StarScript's placeholders.
