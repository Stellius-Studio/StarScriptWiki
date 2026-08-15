## Description
Fires when a player toggles the swimming animation state (`EntityToggleSwimEvent`).


## Config
| Attribute | Description                                            | Default |
|-----------|-----------------------------------------------------------|---------|
| state     | Only fire if the new swimming state matches (`true`/`false`) | any     |


## Skill Variables
| Variable      | Description                       |
|-----------------|----------------------------------------|
| `event-state`     | `true` if the player is now swimming      |


## Examples
```yaml
Skills:
- message{m="<aqua>Started swimming!"} @trigger ~onSwimToggle{state=true}
```
