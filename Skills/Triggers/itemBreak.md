## Description
Fires when a player's item breaks from use (`PlayerItemBreakEvent`).


## Config
| Attribute | Description                                       | Default |
|-----------|-----------------------------------------------------|---------|
| item      | Only fire if the broken item matches this material name | any     |


## Skill Variables
| Variable      | Description                     |
|-----------------|------------------------------------|
| `event-item`      | The material name of the broken item |


## Examples
```yaml
Skills:
- message{m="<red>Your item broke!"} @trigger ~onItemBreak{item=WOODEN_PICKAXE}
```
