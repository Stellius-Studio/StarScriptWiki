## Description
Fires when a player catches fire (`EntityCombustEvent`).


## Config
None.


## Skill Variables
| Variable        | Description                |
|-------------------|--------------------------------|
| `event-duration`    | How many seconds the player will burn for |


## Examples
```yaml
Skills:
- message{m="<red>You're on fire!"} @trigger ~onCombust
```
