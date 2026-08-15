## Description
Fires when a player's game mode changes (`PlayerGameModeChangeEvent`).


## Config
| Attribute | Description                                                  | Default |
|-----------|-------------------------------------------------------------------|---------|
| mode      | Only fire if switching TO this game mode (e.g. `CREATIVE`)            | any     |


## Skill Variables
| Variable          | Description             |
|---------------------|------------------------------|
| `event-gamemode`     | The new game mode's name      |


## Examples
```yaml
Skills:
- message{m="<yellow>Creative mode enabled."} @trigger ~onGamemodeChange{mode=CREATIVE}
```
