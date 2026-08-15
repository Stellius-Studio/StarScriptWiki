## Description
Removes an enchantment from the caster's or targeted entity's item, if present.


## Attributes
| Attribute | Aliases | Description                                                                     | Default |
|-----------|---------|------------------------------------------------------------------------------------|---------|
| enchant   |         | The enchantment's namespaced id                                                    | none (required) |
| slot      |         | Which equipment slot's item to modify — `hand`, `offhand`, `head`, `chest`, `legs`, `feet` | hand |


## Examples
```yaml
Skills:
- removemenchenchant{enchant=mythicenchants:reinforced} @trigger
```


## Aliases
None.
