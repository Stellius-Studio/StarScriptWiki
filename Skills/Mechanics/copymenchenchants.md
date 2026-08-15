## Description
Copies every enchantment from the caster's `fromslot=` item onto a targeted entity's `toslot=`
item. With no explicit target, both the source and destination items are read off the caster
itself — e.g. combining a held enchanted book onto held gear.


## Attributes
| Attribute | Aliases | Description                                                                | Default |
|-----------|---------|-----------------------------------------------------------------------------|---------|
| fromslot  |         | Which equipment slot to copy enchantments from — `hand`, `offhand`, `head`, `chest`, `legs`, `feet` | hand |
| toslot    |         | Which equipment slot to copy enchantments onto — `hand`, `offhand`, `head`, `chest`, `legs`, `feet` | offhand |


## Examples
```yaml
Skills:
- copymenchenchants{fromslot=hand;toslot=offhand} @trigger
```

```yaml
Skills:
- copymenchenchants{fromslot=hand;toslot=hand} @target
```


## Aliases
None.
