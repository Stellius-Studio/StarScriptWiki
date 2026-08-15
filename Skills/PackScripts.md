## Introduction
Every place StarScript discovers files from its own `plugins/StarScript/scripts/` folder also
searches a mirrored `Scripts/` subtree inside every MythicMobs pack — the base pack
(`plugins/MythicMobs/Scripts/`) and every loaded pack
(`plugins/MythicMobs/packs/<name>/Scripts/`), recursively. This lets an addon/content pack ship
its own scripts, targeters, compound triggers, and extensions alongside its `Mobs:`/`Skills:`/
`DropTables:`/etc. content, instead of requiring a separate drop into StarScript's own data
folder.

Uses MythicMobs' own pack API (`PackManager`/`Pack.getPackFolders`) to find each pack's `Scripts/`
folder — the same mechanism MythicEnchants already uses to load enchantments from
`packs/<name>/Enchantments/`.


## Layout
Each search location mirrors StarScript's own `scripts/` folder exactly — just rooted under a
pack's `Scripts/` folder instead:

```
plugins/MythicMobs/packs/MyAddon/
  Mobs/
    my_mob.yml
  Scripts/
    my_script.yml            <- plain script, same as scripts/my_script.yml
    targeters/
      my_targeter.yml         <- see Targeters
    triggers/
      my_compound_trigger.yml <- see Compound Triggers
    extensions/
      smite.yml                <- see Extension Scripting (Premium)
      SmiteMechanic.java
```

The base pack works the same way, one level up:

```
plugins/MythicMobs/
  Scripts/
    my_script.yml
```

All four content types are discovered from every pack at once (not just one) — a script pack and
a mob pack can each ship their own `Scripts/` folder independently, and everything gets merged
together at load time exactly as if it all lived in one folder.


## Reserved subfolder names
`targeters/`, `triggers/`, and `extensions/` are reserved inside any `Scripts/` folder (both the
plugin's own and a pack's) — a file placed there is only ever picked up by its specialized
manager, never double-parsed as a plain script too.


## Reload behavior
`/mm reload` re-discovers everything from every search location, in the same order as a normal
startup (targeters → compound triggers → extensions → scripts) — see
[Extension Scripting](Skills-extensions)'s reload section for how extensions specifically behave.


## See Also
- [Scripts](Skills-Scripts) — the basic script file format.
- [Targeters](Skills-Targeters) — `scripts/targeters/*.yml` / `Scripts/targeters/*.yml`.
- [Compound Triggers](Skills-CompoundTriggers) — `scripts/triggers/*.yml` / `Scripts/triggers/*.yml`.
- [Extension Scripting](Skills-extensions) — `scripts/extensions/**` / `Scripts/extensions/**` (Premium).
