## Description
Fires when a player crosses into a persisted named region (see `createregion`). Detected by
diffing the player's current region set on movement, teleport, and respawn — not tied to any
single Bukkit event.


## Config
| Attribute | Description                  | Default |
|-----------|-----------------------------------|---------|
| id        | Only fire for this region's id      | any region |


## Skill Variables
| Variable      | Description          |
|---------------|---------------------------|
| `event-region`  | The entered region's id  |


## Examples
```yaml
Skills:
- message{m="<green>Welcome to <skill.var.event-region>!"} @trigger ~onRegionEnter{id=spawn_area}
```
