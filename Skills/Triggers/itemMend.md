## Description
Fires when a player's item is repaired by Mending (`PlayerItemMendEvent`).


## Config
None.


## Skill Variables
| Variable       | Description                    |
|------------------|------------------------------------|
| `event-item`       | The material name of the repaired item |
| `event-amount`     | The amount of durability repaired      |


## Examples
```yaml
Skills:
- message{m="<green>Item mended!"} @trigger ~onItemMend
```
