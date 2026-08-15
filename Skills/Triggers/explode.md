## Description
Fires when an entity explodes (`EntityExplodeEvent`).


## Config
| Attribute | Description                                | Default |
|-----------|-------------------------------------------------|---------|
| entity    | Only fire if the exploding entity's type matches   | any     |


## Skill Variables
| Variable       | Description                    |
|------------------|--------------------------------------|
| `event-entity`     | The exploding entity's type name        |


## Examples
```yaml
Skills:
- message{m="<red>Creeper exploded!"} @trigger ~onExplode{entity=CREEPER}
```
