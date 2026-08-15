## Description
With `enchant=` set, true if that specific enchantment id is a curse. With `enchant=` omitted,
true if the caster's item carries ANY cursed MythicEnchants enchantment.


## Attributes
| Attribute | Aliases | Description                                                                | Default |
|-----------|---------|------------------------------------------------------------------------------|---------|
| enchant   |         | The enchantment's namespaced id to check (omit to check the whole item instead) | none (item-wide check) |
| slot      |         | Which equipment slot's item to check — `hand`, `offhand`, `head`, `chest`, `legs`, `feet` | hand |


## Examples
```yaml
Skills:
- message{m="mythicenchants:doom is a curse!"} ?ismenchcursed{enchant=mythicenchants:doom} @trigger
```

```yaml
Skills:
- message{m="This item carries a curse!"} ?ismenchcursed{} @trigger
```


## Aliases
None.
