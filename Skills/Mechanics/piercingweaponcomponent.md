## Description
Marks an item as a piercing (trident-style) weapon, whose hits pass through multiple entities.


## Attributes
| Attribute       | Aliases | Description                                                              | Default |
|-----------------|---------|----------------------------------------------------------------------------------|---------|
| slot            |         | Which equipment slot to affect: `hand` (default), `offhand`, `head`, `chest`, `legs`, `feet` | hand    |
| dealsknockback  |         | Whether hits apply knockback                                                     | true    |
| dismounts       |         | Whether hits dismount the target's rider                                         | false   |
| sound           |         | Namespaced sound key played on throw/trigger                                     | none    |
| hitsound        |         | Namespaced sound key played on hit                                               | none    |


## Examples
```yaml
MakeCustomTrident:
  Skills:
  - piercingweaponcomponent{dealsknockback=true;dismounts=true;hitsound="minecraft:item.trident.hit"} @self
```


## Aliases
None.
