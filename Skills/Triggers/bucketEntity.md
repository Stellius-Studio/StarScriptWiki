## Description
Fires when a player buckets an entity (e.g. scooping up a fish or axolotl)
(`PlayerBucketEntityEvent`). The target is the bucketed entity.


## Config
| Attribute | Description                                | Default |
|-----------|-------------------------------------------------|---------|
| entity    | Only fire if the bucketed entity's type matches    | any     |


## Skill Variables
| Variable       | Description                    |
|------------------|--------------------------------------|
| `event-entity`     | The bucketed entity's type name         |


## Examples
```yaml
Skills:
- message{m="<aqua>Bucketed a fish!"} @trigger ~onBucketEntity{entity=COD}
```
