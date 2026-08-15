## Description
Removes the given data component from an item — a generic escape hatch for any data component
not covered by a dedicated mechanic.


## Attributes
| Attribute | Aliases | Description                                                              | Default |
|-----------|---------|----------------------------------------------------------------------------------|---------|
| slot      |         | Which equipment slot to affect: `hand` (default), `offhand`, `head`, `chest`, `legs`, `feet` | hand    |
| component |         | Namespaced data-component registry key to remove (e.g. `minecraft:food`)         | none (required) |


## Examples
```yaml
StripFoodComponent:
  Skills:
  - clearcomponent{component="minecraft:food"} @self
```


## Aliases
None.
