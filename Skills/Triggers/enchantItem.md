## Description
Fires when a player enchants an item at an enchanting table (`EnchantItemEvent`).


## Config
| Attribute | Description                                       | Default |
|-----------|-----------------------------------------------------|---------|
| item      | Only fire if the enchanted item matches this material name | any     |


## Skill Variables
| Variable      | Description                    |
|-----------------|--------------------------------------|
| `event-item`      | The enchanted item's material name      |
| `event-cost`      | The XP level cost of the enchant          |


## Examples
```yaml
Skills:
- message{m="<aqua>Enchanted for <skill.var.event-cost> levels"} @trigger ~onEnchantItem
```
