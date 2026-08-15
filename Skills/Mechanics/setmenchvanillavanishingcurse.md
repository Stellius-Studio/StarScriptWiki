## Description
Sets or clears MythicEnchants' own tracking marker for the vanilla Curse of Vanishing on the
caster's or targeted entity's item.


## Attributes
| Attribute | Aliases | Description                                                                     | Default |
|-----------|---------|------------------------------------------------------------------------------------|---------|
| state     |         | Whether the vanilla Curse of Vanishing marker should be set                        | true |
| slot      |         | Which equipment slot's item to modify — `hand`, `offhand`, `head`, `chest`, `legs`, `feet` | hand |


## Examples
```yaml
Skills:
- setmenchvanillavanishingcurse{state=true} @trigger
```


## Aliases
None.
