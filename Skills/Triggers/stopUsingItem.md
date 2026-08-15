## Description
Fires when a player stops using an item (e.g. releasing a bow or finishing eating)
(`PlayerStopUsingItemEvent`).


## Config
| Attribute | Description                                       | Default |
|-----------|-----------------------------------------------------|---------|
| item      | Only fire if the used item matches this material name | any     |


## Skill Variables
| Variable      | Description                       |
|-----------------|----------------------------------------|
| `event-item`      | The material name of the used item        |
| `event-ticks`     | How many ticks the item was held for        |


## Examples
```yaml
Skills:
- message{m="<aqua>Stopped using item after <skill.var.event-ticks> ticks"} @trigger ~onStopUsingItem
```
