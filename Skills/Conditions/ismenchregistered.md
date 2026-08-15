## Description
True if the given id is a registered MythicEnchants enchantment.


## Attributes
| Attribute | Aliases | Description                 | Default |
|-----------|---------|--------------------------------|---------|
| enchant   |         | The enchantment's namespaced id | none (required) |


## Examples
```yaml
Skills:
- message{m="Unknown enchant!"} ?ismenchregistered{enchant=mythicenchants:reinforced;NOT} @trigger
```


## Aliases
None.
