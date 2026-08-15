## Description
Fires when a mob spawner spawns an entity (`org.bukkit.event.entity.SpawnerSpawnEvent`). The
target is the spawned entity.


## Config
| Attribute | Description                                | Default |
|-----------|-------------------------------------------------|---------|
| entity    | Only fire if the spawned entity's type matches    | any     |


## Skill Variables
| Variable       | Description                                                   |
|----------------|--------------------------------------------------------------------|
| `event-entity`   | The spawned entity's type name                                    |
| `event-spawner`  | The spawner block's location, as `x,y,z` (only if a spawner block is known) |


## Examples
```yaml
Skills:
- message{m="<gray>Spawner activity: <skill.var.event-entity> at <skill.var.event-spawner>"} ~onSpawnerSpawn
```
