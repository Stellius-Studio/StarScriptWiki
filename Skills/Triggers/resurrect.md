## Description
Fires when a player is resurrected by a Totem of Undying (`EntityResurrectEvent`).


## Config
None.


## Skill Variables
| Variable     | Description                                |
|----------------|------------------------------------------------|
| `event-hand`     | Which hand held the totem (`HAND` or `OFF_HAND`)  |


## Examples
```yaml
Skills:
- message{m="<gold>Resurrected!"} @trigger ~onResurrect
```
