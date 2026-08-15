## Description
Fires when a player mounts an entity (`EntityMountEvent`). The target is the mounted entity.


## Config
| Attribute | Description                                | Default |
|-----------|-------------------------------------------------|---------|
| entity    | Only fire if the mounted entity's type matches     | any     |


## Skill Variables
| Variable       | Description                 |
|------------------|----------------------------------|
| `event-entity`     | The mounted entity's type name       |


## Examples
```yaml
Skills:
- message{m="<aqua>Mounted!"} @trigger ~onMount{entity=HORSE}
```


## See Also
- [dismount](Skills-Triggers-dismount) — the counterpart trigger.
