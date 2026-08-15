## Description
Fires when a player's food level changes (`FoodLevelChangeEvent`).


## Config
None.


## Skill Variables
| Variable      | Description             |
|-----------------|-----------------------------|
| `event-level`     | The new food level (0-20)  |


## Examples
```yaml
Skills:
- message{m="<aqua>Food level: <skill.var.event-level>"} @trigger ~onFoodChange
```
