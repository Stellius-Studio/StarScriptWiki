## Description
Fires when a player tames an animal (`EntityTameEvent`). The target is the tamed entity.


## Config
| Attribute | Description                                | Default |
|-----------|-------------------------------------------------|---------|
| entity    | Only fire if the tamed entity's type matches       | any     |


## Skill Variables
| Variable       | Description                 |
|------------------|----------------------------------|
| `event-entity`     | The tamed entity's type name       |


## Examples
```yaml
Skills:
- message{m="<green>Tamed a wolf!"} @trigger ~onTame{entity=WOLF}
```
