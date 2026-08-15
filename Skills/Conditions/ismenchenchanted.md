## Description
True if the caster's item carries at least one MythicEnchants-registered enchantment.


## Attributes
| Attribute | Aliases | Description                                                                | Default |
|-----------|---------|------------------------------------------------------------------------------|---------|
| slot      |         | Which equipment slot's item to check — `hand`, `offhand`, `head`, `chest`, `legs`, `feet` | hand |


## Examples
```yaml
Skills:
- message{m="That item has no MythicEnchants enchantments."} ?ismenchenchanted{NOT} @trigger
```


## Aliases
None.
