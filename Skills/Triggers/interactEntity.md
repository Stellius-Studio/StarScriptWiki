## Description
Fires when a player right-clicks an entity (`PlayerInteractEntityEvent`). The target is the
right-clicked entity.


## Config
| Attribute | Description                        | Default |
|-----------|-----------------------------------------|---------|
| entity    | Only fire if the entity type matches        | any     |


## Skill Variables
| Variable        | Description               |
|-------------------|---------------------------------|
| `event-entity`     | The right-clicked entity's type name |


## Examples
```yaml
Skills:
- message{m="<aqua>You petted the wolf!"} @trigger ~onInteractEntity{entity=WOLF}
```
