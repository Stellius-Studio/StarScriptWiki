## Description
Fires when a player breeds two animals (`EntityBreedEvent`). The target is the resulting baby
entity.


## Config
| Attribute | Description                                | Default |
|-----------|-------------------------------------------------|---------|
| entity    | Only fire if the baby entity's type matches        | any     |


## Skill Variables
| Variable       | Description               |
|------------------|--------------------------------|
| `event-entity`     | The baby entity's type name      |


## Examples
```yaml
Skills:
- message{m="<green>New cow born!"} @trigger ~onBreed{entity=COW}
```
