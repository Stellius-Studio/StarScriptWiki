## Description
Fires when a player's XP level changes (`PlayerLevelChangeEvent`).


## Config
| Attribute | Description                       | Default |
|-----------|-----------------------------------------|---------|
| min       | Only fire if the new XP level is >= this      | any     |


## Skill Variables
| Variable           | Description             |
|----------------------|------------------------------|
| `event-old-level`     | The previous XP level (int)   |
| `event-new-level`     | The new XP level (int)        |


## Examples
```yaml
Skills:
- message{m="<gold>You reached level <skill.var.event-new-level>!"} @trigger ~onLevelChange{min=5}
```
