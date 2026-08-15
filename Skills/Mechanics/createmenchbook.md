## Description
Builds an enchanted book carrying the given enchantments and gives it to the caster (dropped at
their feet if their inventory is full, or if the caster has no inventory at all).


## Attributes
| Attribute | Aliases | Description                                                                              | Default |
|-----------|---------|--------------------------------------------------------------------------------------------|---------|
| enchants  |         | `;`-delimited `id:level` entries, e.g. `mythicenchants:fire_slash:3;sharpness:2`             | none (required) |


## Examples
```yaml
Skills:
- createmenchbook{enchants=mythicenchants:fire_slash:3;sharpness:2} @trigger
```


## Aliases
None.
