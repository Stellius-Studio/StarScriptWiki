## Description
Fires whenever a player's vanilla statistic increases (`PlayerStatisticIncrementEvent`).


## Config
| Attribute | Description                                      | Default |
|-----------|---------------------------------------------------|---------|
| stat      | Only fire if the statistic's name matches exactly  | any     |


## Skill Variables
| Variable         | Description                                                     |
|------------------|-------------------------------------------------------------------|
| `event-statistic`  | The statistic's enum name                                        |
| `event-previous`   | The statistic's value before the increment                       |
| `event-new`        | The statistic's value after the increment                        |
| `event-material`   | The material qualifier, if this is a block/item-typed statistic  |
| `event-entity`     | The entity type qualifier, if this is an entity-typed statistic  |


## Examples
```yaml
Skills:
- message{m="<green>New personal best: <skill.var.event-new> kills!"} @trigger ~onStatisticIncrement{stat=PLAYER_KILLS}
```
