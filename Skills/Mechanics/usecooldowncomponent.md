## Description
Sets the cooldown applied after using this item, optionally sharing that cooldown across
multiple different items via a cooldown group.


## Attributes
| Attribute | Aliases | Description                                                              | Default |
|-----------|---------|----------------------------------------------------------------------------------|---------|
| slot      |         | Which equipment slot to affect: `hand` (default), `offhand`, `head`, `chest`, `legs`, `feet` | hand    |
| seconds   |         | Cooldown length in seconds (minimum 0.05)                                        | 1.0 (required) |
| group     |         | Namespaced cooldown-group key shared across multiple items                       | none    |


## Examples
```yaml
MakeSlowRelic:
  Skills:
  - usecooldowncomponent{seconds=30;group="mynamespace:relics"} @self
```


## Aliases
None.
