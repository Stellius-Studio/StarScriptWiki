## Description
Fires when a Crafter block is about to craft an item (`CrafterCraftEvent`, requires Minecraft
1.21.1+).


## Config
| Attribute | Description                                       | Default |
|-----------|------------------------------------------------------|---------|
| id        | Only fire if the recipe's namespaced key contains this  | any     |


## Skill Variables
| Variable      | Description                |
|---------------|--------------------------------|
| `event-recipe`  | The used recipe's namespaced key |


## Examples
```yaml
Skills:
- message{m="<gray>A crafter just made: <skill.var.event-recipe>"} ~onCrafterCraft
```
