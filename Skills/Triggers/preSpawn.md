## Description
Fires on every natural-spawn attempt, before the entity actually exists
(`com.destroystokyo.paper.event.entity.PreCreatureSpawnEvent`) — the entity has no UUID/state
yet, only a location, type, and spawn reason. Fires very frequently (every attempt, not just
successful spawns), so keep scripts on this trigger lightweight. `cancel=true` may not
reliably prevent the spawn, since this event uses its own `shouldAbort()` rather than the
standard `Cancellable` contract.


## Config
| Attribute | Description                              | Default |
|-----------|---------------------------------------------|---------|
| entity    | Only fire if the about-to-spawn entity's type matches | any |


## Skill Variables
| Variable       | Description                          |
|----------------|-----------------------------------------|
| `event-entity`   | The about-to-spawn entity's type name  |
| `event-reason`   | The `CreatureSpawnEvent.SpawnReason` name |


## Examples
```yaml
Skills:
- message{m="<gray>A zombie is about to spawn nearby."} ~onPreSpawn{entity=ZOMBIE}
```
