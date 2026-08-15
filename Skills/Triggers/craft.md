## Description
Fires when a player crafts an item (`CraftItemEvent`).


## Config
| Attribute | Description                                       | Default |
|-----------|-----------------------------------------------------|---------|
| item      | Only fire if the crafted item matches this material name | any     |


## Skill Variables
| Variable      | Description                    |
|-----------------|--------------------------------------|
| `event-item`      | The crafted item's material name        |


## Examples
```yaml
Skills:
- message{m="<green>Crafted!"} @trigger ~onCraft{item=DIAMOND_SWORD}
```
