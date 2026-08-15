## Description
Fires when a player gains XP (`PlayerExpChangeEvent`).


## Config
None.


## Skill Variables
| Variable        | Description             |
|-------------------|------------------------------|
| `event-amount`     | The amount of XP gained (int) |


## Examples
```yaml
Skills:
- message{m="<green>+<skill.var.event-amount> XP"} @trigger ~onExpChange
```


## See Also
- [levelChange](Skills-Triggers-levelChange) — fires specifically when the XP level itself changes.
