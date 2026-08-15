## Description
True if the caster's item (typically an enchanted book) carries the given *stored* enchantment
at or above the given level.


## Attributes
| Attribute | Aliases | Description                                                                | Default |
|-----------|---------|------------------------------------------------------------------------------|---------|
| enchant   |         | The enchantment's namespaced id                                              | none (required) |
| level     |         | The minimum level required                                                   | 1 |
| slot      |         | Which equipment slot's item to check — `hand`, `offhand`, `head`, `chest`, `legs`, `feet` | hand |


## Examples
```yaml
Skills:
- message{m="This book stores Reinforced!"} ?hasmenchstoredenchant{enchant=mythicenchants:reinforced} @trigger
```


## Aliases
None.
