## Description
Fires when a player crosses out of a persisted named region (see `createregion`). Detected by
diffing the player's current region set on movement, teleport, and respawn — not tied to any
single Bukkit event.


## Config
| Attribute | Description                  | Default |
|-----------|-----------------------------------|---------|
| id        | Only fire for this region's id      | any region |


## Skill Variables
| Variable      | Description         |
|---------------|--------------------------|
| `event-region`  | The exited region's id  |


## Examples
```yaml
Skills:
- message{m="<yellow>You left <skill.var.event-region>."} @trigger ~onRegionExit{id=spawn_area}
```
