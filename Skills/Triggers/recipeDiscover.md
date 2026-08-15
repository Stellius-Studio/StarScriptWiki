## Description
Fires when a player unlocks a recipe (`PlayerRecipeDiscoverEvent`).


## Config
| Attribute | Description                                       | Default |
|-----------|------------------------------------------------------|---------|
| id        | Only fire if the recipe's namespaced key contains this  | any     |


## Skill Variables
| Variable      | Description                     |
|---------------|-------------------------------------|
| `event-recipe`  | The discovered recipe's namespaced key |


## Examples
```yaml
Skills:
- message{m="<green>New recipe unlocked: <skill.var.event-recipe>"} @trigger ~onRecipeDiscover
```
