## Description
Fires when a player toggles flight (`PlayerToggleFlightEvent`).


## Config
| Attribute | Description                                            | Default |
|-----------|---------------------------------------------------------|---------|
| state     | Only fire if the new flying state matches (`true`/`false`) | any     |


## Skill Variables
| Variable      | Description                     |
|-----------------|------------------------------------|
| `event-state`     | `true` if the player is now flying   |


## Examples
```yaml
Skills:
- message{m="<aqua>You started flying!"} @trigger ~onFlightToggle{state=true}
```
