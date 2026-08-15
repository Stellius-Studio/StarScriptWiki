## Description
Fires when a broken block drops items (`BlockDropItemEvent`). The target location is the broken
block.


## Config
| Attribute | Description                                      | Default |
|-----------|------------------------------------------------------|---------|
| block     | Only fire if the broken block matches this material name | any     |


## Skill Variables
| Variable      | Description                    |
|-----------------|--------------------------------------|
| `event-block`     | The broken block's material name        |


## Examples
```yaml
Skills:
- message{m="<green>Block drop!"} @trigger ~onBlockDropItem{block=STONE}
```
