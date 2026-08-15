## Description
True if the given enchantment id may be traded by villagers.


## Attributes
| Attribute | Aliases | Description                 | Default |
|-----------|---------|--------------------------------|---------|
| enchant   |         | The enchantment's namespaced id | none (required) |


## Examples
```yaml
Skills:
- message{m="Villagers can trade this enchant."} ?ismenchtradeable{enchant=mythicenchants:reinforced} @trigger
```


## Aliases
None.
