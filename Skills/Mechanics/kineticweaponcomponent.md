## Description
Sets an item's kinetic-weapon (mace-style) knockback and dismount properties.


## Attributes
| Attribute            | Aliases | Description                                                              | Default |
|-----------------------|---------|----------------------------------------------------------------------------------|---------|
| slot                  |         | Which equipment slot to affect: `hand` (default), `offhand`, `head`, `chest`, `legs`, `feet` | hand    |
| delayticks            |         | Delay in ticks before the kinetic effect can trigger                             | 0       |
| forwardmovement       |         | Forward movement contribution to the kinetic effect                              | 0.0     |
| damagemultiplier      |         | Multiplier applied to kinetic damage                                             | 1.0     |
| sound                 |         | Namespaced sound key played on trigger                                           | none    |
| hitsound              |         | Namespaced sound key played on hit                                               | none    |
| damageconditions      |         | Conditions gating bonus damage — `maxDurationTicks:minSpeed:minRelativeSpeed`     | none    |
| dismountconditions    |         | Conditions gating rider dismount — same syntax as `damageconditions=`            | none    |
| knockbackconditions   |         | Conditions gating knockback — same syntax as `damageconditions=`                 | none    |


## Examples
```yaml
MakeCustomMace:
  Skills:
  - kineticweaponcomponent{delayticks=0;damagemultiplier=1.5;damageconditions="20:0:0.1";knockbackconditions="20:0:0.1"} @self
```


## Aliases
None.
