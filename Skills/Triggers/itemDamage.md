## Description
Fires when a player's item takes durability damage (`PlayerItemDamageEvent`).


## Config
| Attribute | Description                                       | Default |
|-----------|-----------------------------------------------------|---------|
| item      | Only fire if the damaged item matches this material name | any     |


## Skill Variables
| Variable       | Description                        |
|------------------|----------------------------------------|
| `event-item`       | The material name of the damaged item     |
| `event-damage`     | The amount of durability damage taken      |


## Examples
```yaml
Skills:
- message{m="<red>Item took damage!"} @trigger ~onItemDamage
```
