## Description
Fires when a player unleashes an entity (`PlayerUnleashEntityEvent`). The target is the
unleashed entity.


## Config
| Attribute | Description                                | Default |
|-----------|-------------------------------------------------|---------|
| entity    | Only fire if the unleashed entity's type matches   | any     |


## Skill Variables
| Variable       | Description                    |
|------------------|--------------------------------------|
| `event-entity`     | The unleashed entity's type name        |


## Examples
```yaml
Skills:
- message{m="<aqua>Unleashed!"} @trigger ~onUnleash
```


## See Also
- [leash](Skills-Triggers-leash) — the counterpart trigger.
