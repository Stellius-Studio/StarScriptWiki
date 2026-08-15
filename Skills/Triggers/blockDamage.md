## Description
Fires when a player starts damaging a block (`BlockDamageEvent`). The target location is the
damaged block.


## Config
| Attribute | Description                                      | Default |
|-----------|------------------------------------------------------|---------|
| block     | Only fire if the damaged block matches this material name | any     |


## Skill Variables
| Variable      | Description                     |
|-----------------|--------------------------------------|
| `event-block`     | The damaged block's material name       |


## Examples
```yaml
Skills:
- message{m="<red>Digging..."} @trigger ~onBlockDamage
```
