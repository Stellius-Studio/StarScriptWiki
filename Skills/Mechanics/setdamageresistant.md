## Description
Makes an item immune to a whole damage-type tag when worn (armor) or held.


## Attributes
| Attribute | Aliases | Description                                                              | Default |
|-----------|---------|----------------------------------------------------------------------------------|---------|
| slot      |         | Which equipment slot to affect: `hand` (default), `offhand`, `head`, `chest`, `legs`, `feet` | hand    |
| tag       |         | Damage-type tag key the item is resistant to (e.g. `minecraft:is_fire`)          | none (required) |


## Examples
```yaml
MakeFireproofArmor:
  Skills:
  - setdamageresistant{slot=chest;tag="minecraft:is_fire"} @self
```


## Aliases
None.
