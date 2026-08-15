## Description
Fires when a player toggles sprinting (`PlayerToggleSprintEvent`).


## Config
| Attribute | Description                                                                        | Default |
|-----------|-------------------------------------------------------------------------------------------|---------|
| state     | Only fire when transitioning to this specific sprinting state (`true`/`false`); unset fires on both sprint start and stop | any     |


## Skill Variables
| Variable       | Description                    |
|------------------|--------------------------------------|
| `event-state`     | The new sprinting state (boolean)     |


## Examples
```yaml
Skills:
- message{m="<gray>You feel winded."} @trigger ~onSprint{state=false}
```


## See Also
- [sneak](Skills-Triggers-sneak) — the sneaking equivalent.
