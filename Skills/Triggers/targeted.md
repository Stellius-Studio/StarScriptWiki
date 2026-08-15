## Description
Fires when a mob targets a player (`EntityTargetEvent`). The target is the targeting mob.


## Config
| Attribute | Description                                       | Default |
|-----------|-----------------------------------------------------|---------|
| entity    | Only fire if the targeting mob's entity type matches | any     |


## Skill Variables
| Variable       | Description                    |
|------------------|-------------------------------------|
| `event-entity`     | The targeting mob's entity type name |


## Examples
```yaml
Skills:
- message{m="<red>A zombie noticed you!"} @trigger ~onTargeted{entity=ZOMBIE}
```
