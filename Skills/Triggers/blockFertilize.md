## Description
Fires when a block is fertilized with bonemeal (`BlockFertilizeEvent`). Fires with a player
context if a player caused it, otherwise a location-only context. The target location is the
fertilized block.


## Config
| Attribute | Description                                      | Default |
|-----------|------------------------------------------------------|---------|
| block     | Only fire if the fertilized block matches this material name | any     |


## Skill Variables
| Variable      | Description                     |
|-----------------|--------------------------------------|
| `event-block`     | The fertilized block's material name    |


## Examples
```yaml
Skills:
- message{m="<green>Fertilized!"} @trigger ~onBlockFertilize
```
