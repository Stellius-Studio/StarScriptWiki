## Description
True if the given enchantment id is treasure-only.


## Attributes
| Attribute | Aliases | Description                 | Default |
|-----------|---------|--------------------------------|---------|
| enchant   |         | The enchantment's namespaced id | none (required) |


## Examples
```yaml
Skills:
- message{m="That's a treasure enchant!"} ?ismenchtreasure{enchant=mythicenchants:soulbound} @trigger
```


## Aliases
None.
