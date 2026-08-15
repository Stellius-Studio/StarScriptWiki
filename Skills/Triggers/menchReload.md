## Description
Fires when MythicEnchants reloads (`MenchReloadEvent`) — datapack regeneration, a skills reload,
or a config reload. Not player-scoped (there's no casting entity for a server-wide reload), so
this trigger's skill context uses a virtual location at the default world's spawn point instead of
a player/entity.


## Config
| Attribute | Description                                                 | Default |
|-----------|------------------------------------------------------------------|---------|
| kind      | Only fire if the reload kind matches — `DATAPACK`, `SKILLS`, or `CONFIGS` | any     |


## Skill Variables
| Variable      | Description                          |
|---------------|-------------------------------------------|
| `event-kind`    | The reload kind — `DATAPACK`, `SKILLS`, or `CONFIGS` |


## Examples
```yaml
Skills:
- broadcast{m="<yellow>MythicEnchants reloaded (<skill.var.event-kind>)."} @trigger ~onMenchReload
```

```yaml
Skills:
- broadcast{m="<yellow>MythicEnchants datapack regenerated."} @trigger ~onMenchReload{kind=DATAPACK}
```
