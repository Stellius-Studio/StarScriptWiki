## Description
Fires when a player completes an advancement (`PlayerAdvancementDoneEvent`).


## Config
| Attribute | Description                                                          | Default |
|-----------|---------------------------------------------------------------------------|---------|
| key       | Only fire if the advancement's namespaced key CONTAINS this substring (e.g. `story/mine_diamond`) | any     |


## Skill Variables
| Variable             | Description                       |
|------------------------|-----------------------------------------|
| `event-advancement`     | The full advancement key string            |


## Examples
```yaml
Skills:
- broadcast{m="<gold><trigger.name> struck gold — literally!"} @trigger ~onAdvancement{key=story/mine_diamond}
```
