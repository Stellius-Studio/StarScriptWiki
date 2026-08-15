## Description
Sets the "enchantment value" that governs how enchantable an item is — higher values offer
more/better enchantments at an enchanting table.


## Attributes
| Attribute | Aliases | Description                                                              | Default |
|-----------|---------|----------------------------------------------------------------------------------|---------|
| slot      |         | Which equipment slot to affect: `hand` (default), `offhand`, `head`, `chest`, `legs`, `feet` | hand    |
| value     |         | Enchantment value (minimum 1)                                                    | 1 (required) |


## Examples
```yaml
MakeHighlyEnchantableItem:
  Skills:
  - setenchantablecomponent{value=25} @self
```


## Aliases
None.
