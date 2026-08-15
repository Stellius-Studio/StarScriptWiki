## Description
Fires when any entity spawns (`EntitySpawnEvent`) — not restricted to player-caused spawns. The
target is the spawned entity.


## Config
| Attribute | Description                                                       | Default |
|-----------|-----------------------------------------------------------------------|---------|
| entity    | Only fire if the entity type matches (comma-separated list allowed)     | any     |
| mythicmob | Only fire if the entity is a MythicMobs mob with this internal name     | any     |


## Skill Variables
| Variable            | Description                                       |
|-----------------------|--------------------------------------------------------|
| `event-entity`          | The spawned entity's type name                          |
| `event-mythic-type`     | The MythicMobs internal type name (empty if not a MythicMob) |


## Examples
```yaml
Skills:
- message{m="<red>A zombie spawned!"} @trigger ~onEntitySpawn{entity=ZOMBIE}
```
