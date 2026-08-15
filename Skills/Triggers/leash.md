## Description
Fires when a player leashes an entity (`PlayerLeashEntityEvent`). The target is the leashed
entity.


## Config
| Attribute | Description                                | Default |
|-----------|-------------------------------------------------|---------|
| entity    | Only fire if the leashed entity's type matches     | any     |


## Skill Variables
| Variable       | Description                  |
|------------------|-----------------------------------|
| `event-entity`     | The leashed entity's type name       |


## Examples
```yaml
Skills:
- message{m="<aqua>Leashed!"} @trigger ~onLeash
```


## See Also
- [unleash](Skills-Triggers-unleash) — the counterpart trigger.
