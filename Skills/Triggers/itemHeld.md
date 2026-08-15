## Description
Fires when a player changes their held hotbar slot (`PlayerItemHeldEvent`).


## Config
None.


## Skill Variables
| Variable      | Description                             |
|-----------------|----------------------------------------------|
| `event-slot`     | The new held hotbar slot index (int, 0-8)     |


## Examples
```yaml
Skills:
- message{m="<gray>Now holding slot <skill.var.event-slot>."} @trigger ~onItemHeld
```
