## Description
True if the caster's item carries the given enchantment at or above the given level.


## Attributes
| Attribute | Aliases | Description                                                                | Default |
|-----------|---------|------------------------------------------------------------------------------|---------|
| enchant   |         | The enchantment's namespaced id                                              | none (required) |
| level     |         | The minimum level required                                                   | 1 |
| slot      |         | Which equipment slot's item to check — `hand`, `offhand`, `head`, `chest`, `legs`, `feet` | hand |


## Examples
```yaml
Skills:
- message{m="Your weapon is Reinforced!"} ?hasmenchenchant{enchant=mythicenchants:reinforced} @trigger
```

```yaml
Skills:
- message{m="Reinforced III or higher!"} ?hasmenchenchant{enchant=mythicenchants:reinforced;level=3} @trigger
```


## Aliases
None.
