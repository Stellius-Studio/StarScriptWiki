## Description
Sets which materials can repair this item at an anvil.


## Attributes
| Attribute | Aliases | Description                                                              | Default |
|-----------|---------|----------------------------------------------------------------------------------|---------|
| slot      |         | Which equipment slot to affect: `hand` (default), `offhand`, `head`, `chest`, `legs`, `feet` | hand    |
| items     |         | CSV of material names that can repair this item                                  | none (required) |


## Examples
```yaml
MakeRepairableWithNetherite:
  Skills:
  - setrepairablecomponent{items="NETHERITE_INGOT"} @self
```


## Aliases
None.
