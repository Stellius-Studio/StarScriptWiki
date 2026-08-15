## Description
Fires when a player dismounts an entity (`EntityDismountEvent`). The target is the dismounted
entity.


## Config
| Attribute | Description                                | Default |
|-----------|-------------------------------------------------|---------|
| entity    | Only fire if the dismounted entity's type matches  | any     |


## Skill Variables
| Variable       | Description                     |
|------------------|--------------------------------------|
| `event-entity`     | The dismounted entity's type name       |


## Examples
```yaml
Skills:
- message{m="<aqua>Dismounted!"} @trigger ~onDismount
```


## See Also
- [mount](Skills-Triggers-mount) — the counterpart trigger.
