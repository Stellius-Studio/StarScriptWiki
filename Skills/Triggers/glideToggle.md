## Description
Fires when a player toggles gliding with an elytra (`EntityToggleGlideEvent`).


## Config
| Attribute | Description                                            | Default |
|-----------|-----------------------------------------------------------|---------|
| state     | Only fire if the new gliding state matches (`true`/`false`) | any     |


## Skill Variables
| Variable      | Description                     |
|-----------------|------------------------------------|
| `event-state`     | `true` if the player is now gliding   |


## Examples
```yaml
Skills:
- message{m="<aqua>Started gliding!"} @trigger ~onGlideToggle{state=true}
```
