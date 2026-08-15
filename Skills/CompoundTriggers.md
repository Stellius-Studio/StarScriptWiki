## Introduction
StarScript lets you define your **own** named triggers in YAML, built by combining several
existing `~onX` triggers (StarScript's own catalog or any MythicMobs-native trigger name) into
one reusable `~onName` token — usable anywhere a trigger token is used, exactly like a built-in
one.

Two modes:

- **`Mode: any`** (OR) — fires every time *any* listed trigger fires, optionally gated by a
  shared condition list checked against whoever triggered it. Stateless.
- **`Mode: all`** (AND, any order) — tracks, per player, which of the listed triggers have
  fired at least once; once *all* of them have (in any order, over any timespan), the compound
  trigger fires once and progress resets.


## Defining a compound trigger
Drop one or more `.yml` files in `plugins/StarScript/scripts/triggers/`. Each top-level key
becomes a trigger name, usable as `~onName` on any skill line or `Events:` entry, in any script.

```yaml
# scripts/triggers/onplayerhurt.yml
onPlayerHurt:
  Mode: any
  Triggers:
    - damage
    - damageByEntity
  Conditions:
    - hasscoreboardtag{tag=vip}
```

```yaml
NotifyVipHurt:
  Skills:
  - message{m="<red>Ouch!"} @trigger ~onPlayerHurt
```

`onPlayerHurt` fires whenever a VIP player takes damage from either cause — `damage` OR
`damageByEntity`, filtered by the shared `Conditions:` list (checked against whoever the
underlying trigger's own extractor resolved as caster).


## `Mode: all` — any-order sequences
```yaml
# scripts/triggers/veteranready.yml
veteranReady:
  Mode: all
  Persist: true
  Triggers:
    - join
    - levelChange{min=10}
    - entityKill{entity=ZOMBIE}
```

```yaml
WelcomeVeteran:
  Skills:
  - message{m="<gold>Welcome, veteran!"} @trigger ~onVeteranReady
```

`veteranReady` fires once a player has, at some point, joined the server, reached level 10, and
killed a zombie — **in any order**, not necessarily in one session. Once all three have
happened, it fires once and that player's progress resets (so it can fire again from scratch if
they somehow "un-qualify" and re-qualify later — StarScript doesn't guard against that, it's
just a fresh count).

`Persist: true` (only meaningful for `Mode: all`) saves progress via the same storage layer
behind `setstorage`/`getstorage`, so a player who's done 2 of 3 steps keeps that progress across
a server restart. Without it (the default), progress is in-memory only and resets on restart.


## Per-trigger config
Each entry in `Triggers:` keeps its own inline config exactly as written — `levelChange{min=10}`
only counts as "step complete" once the player actually reaches level 10, same as if you'd
written that trigger directly on a skill line. Mixing StarScript's own catalog names and raw
MythicMobs trigger names in the same list is fine, same as anywhere else triggers are used.


## Notes
- A `Triggers:` list needs at least 2 valid entries; an unknown trigger name in the list is
  skipped with a warning (check `/starscript reload`'s output), and if fewer than 2 valid
  entries remain the whole definition is skipped.
- `Mode: all` progress is tracked per **player** — a non-player caster (e.g. a MythicMob itself
  triggering one of the listed events) doesn't count toward or complete a sequence.
- The shared `Conditions:` list (both modes) is checked against whoever the *firing* trigger's
  own extractor resolved as caster — same per-entity condition evaluation used by
  [Targeters](Skills-Targeters)' definition-level condition list.
- Reload with `/starscript reload` (or `/mm reload`, which also triggers a StarScript
  reload) — compound triggers are (re)registered before scripts are parsed, so a script
  referencing `~onName` always resolves regardless of file load order.

#

## See Also
- [Triggers](Skills-Triggers) — the full built-in `~onX` catalog these are built from.
- [Targeters](Skills-Targeters) — the same YAML-defined-dynamic-name pattern, for targeters.
- [Scripts](Skills-Scripts) — how triggers fit into a script's `Skills:` list.
- [Pack Scripts](Skills-PackScripts) — compound trigger files are also discovered from
  `Scripts/triggers/` inside any MythicMobs pack, not just StarScript's own data folder.
