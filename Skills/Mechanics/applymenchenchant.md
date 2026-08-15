## Description
Applies (or overwrites) a MythicEnchants/vanilla enchantment on the caster's or targeted entity's
item.


## Attributes
| Attribute   | Aliases | Description                                                                     | Default |
|-------------|---------|----------------------------------------------------------------------------------|---------|
| enchant     |         | The enchantment's namespaced id                                                  | none (required) |
| level       |         | The enchantment level to apply                                                   | 1 |
| firetrigger |         | Whether to fire MythicEnchants' `ENCHANT_APPLY` trigger for the affected player  | false |
| slot        |         | Which equipment slot's item to modify — `hand`, `offhand`, `head`, `chest`, `legs`, `feet` | hand |


## Examples
```yaml
Skills:
- applymenchenchant{enchant=mythicenchants:reinforced;level=3} @trigger
```

```yaml
Skills:
- applymenchenchant{enchant=mythicenchants:reinforced;level=2;firetrigger=true;slot=offhand} @target
```


## Aliases
None.
