## Introduction
StarScript scripts get every MythicMobs targeter for free. On top of that, StarScript lets
you define your **own** named targeters in YAML — each one wraps one or more base targeters and
unions their entities together.


## Built-in: `@onlineplayers`
Targets every online player, caster included. Functionally identical to MythicMobs' own
`@playersOnServer` (aliases `@server`/`@everyone`) — added under a clearer name, since `@server`
reads as "the server itself" rather than "everyone connected to it".

```yaml
AnnounceAll:
  Skills:
  - message{m="<gold>A wild event has started!"} @onlineplayers
```


## Defining a targeter
Drop one or more `.yml` files in `plugins/StarScript/scripts/targeters/`. Each top-level key
in the file becomes a targeter name, usable as `@name` on any skill line, anywhere in any
script — exactly like a built-in MythicMobs targeter.

Each name maps to a list of targeter expressions. Every entry's name must match a targeter
already registered with MythicMobs (built-in or from any plugin, including other
StarScript-defined targeters loaded earlier) — list more than one to union their entities
together (duplicates removed).

```yaml
# scripts/targeters/vip.yml
vipnearby:
  - EntitiesInRadius{r=15}
```

```yaml
SomeScript:
  Skills:
  - heal{amount=10} @vipnearby
```

Multiple targeter definitions can live in one file, and multiple files can live in the
`targeters/` folder — they're all discovered and loaded together, the same way `scripts/*.yml`
is scanned for scripts. Reload with `/starscript reload` (or `/mm reload`, which also
triggers a StarScript reload).

Each entry keeps its own inline MythicMobs config exactly as written, including MythicMobs' own
native `c=`/`conditions=`/`targetconditions=` gate (e.g. `Owner{c=[hasaura{aura=Plagued}]}`) — a
**MythicMobs Premium feature**, all-or-nothing, checked once against the casting context. If it
fails, that one base targeter contributes nothing to the union; the rest of the definition is
unaffected.


## More examples
```yaml
sleepingplayers:
  - PlayersInRadius{r=20}

triggerisplayer:
  - Trigger

# Multiple base targeters unioned together.
sleepyneighbors:
  - PlayersInRadius{r=10}
  - MobsInRadius{r=10}
```

```yaml
SleepingPlayersOnly:
  Skills:
  - message{m="You're asleep!"} @sleepingplayers

FilteredTrigger:
  Skills:
  - damage{amount=5} @triggerisplayer

WakeEveryone:
  Skills:
  - sound{s=entity.player.levelup} @sleepyneighbors
```


## Notes
- If no entry in a definition's list matches a known targeter name, that definition is skipped
  (with a warning) — check `/starscript reload`'s output.
- Listing multiple targeter entries unions their entity pools (deduplicated by UUID).
- A targeter name only becomes available once MythicMobs actually needs to resolve it — so load
  order between `targeters/` files and the scripts that reference them doesn't matter.


## See Also
- [Scripts](Skills-Scripts) — how targeters fit into a script's `Skills:` list.
- [Conditions](Skills-Conditions) — StarScript's custom conditions.
- [Mechanics](Skills-Mechanics) — StarScript's custom mechanics.
- [Compound Triggers](Skills-CompoundTriggers) — the same YAML-defined-dynamic-name pattern,
  for triggers.
- [Pack Scripts](Skills-PackScripts) — targeter files are also discovered from
  `Scripts/targeters/` inside any MythicMobs pack, not just StarScript's own data folder.
