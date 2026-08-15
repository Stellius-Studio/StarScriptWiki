## Description
True if the given enchantment is valid for the caster's item — registered, enabled, and passes
any restriction/tag checks.


## Attributes
| Attribute | Aliases | Description                                                                | Default |
|-----------|---------|------------------------------------------------------------------------------|---------|
| enchant   |         | The enchantment's namespaced id                                              | none (required) |
| slot      |         | Which equipment slot's item to check — `hand`, `offhand`, `head`, `chest`, `legs`, `feet` | hand |


## Examples
```yaml
Skills:
- applymenchenchant{enchant=mythicenchants:reinforced;level=1} ?ismenchenchantvalidfor{enchant=mythicenchants:reinforced} @trigger
```


## Aliases
None.
