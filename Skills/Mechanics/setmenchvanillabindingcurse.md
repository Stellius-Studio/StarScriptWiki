## Description
Sets or clears MythicEnchants' own tracking marker for the vanilla Curse of Binding on the
caster's or targeted entity's item. This is distinct from MythicEnchants' own `Cursed:`
enchantment option — it only tracks the vanilla Minecraft curse enchantment.


## Attributes
| Attribute | Aliases | Description                                                                     | Default |
|-----------|---------|------------------------------------------------------------------------------------|---------|
| state     |         | Whether the vanilla Curse of Binding marker should be set                          | true |
| slot      |         | Which equipment slot's item to modify — `hand`, `offhand`, `head`, `chest`, `legs`, `feet` | hand |


## Examples
```yaml
Skills:
- setmenchvanillabindingcurse{state=true} @trigger
```

```yaml
Skills:
- setmenchvanillabindingcurse{state=false;slot=head} @trigger
```


## Aliases
None.
