## Description
True if the caster's main-hand item has the given data component set. A generic escape hatch
for any data component not covered by a dedicated condition.


## Attributes
| Attribute | Aliases | Description                                                              | Default |
|-----------|---------|----------------------------------------------------------------------------------|---------|
| component |         | Namespaced data-component registry key to check for (e.g. `minecraft:food`)      | none (required) |


## Examples
```yaml
Skills:
- message{m="that item is edible"} ?hascomponent{component="minecraft:food"} @trigger
```


## Aliases
None.
