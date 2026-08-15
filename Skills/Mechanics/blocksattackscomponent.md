## Description
Makes an item block attacks when used (shield-style), with optional per-damage-type reductions.


## Attributes
| Attribute             | Aliases | Description                                                              | Default |
|------------------------|---------|--------------------------------------------------------------------------------|---------|
| slot                   |         | Which equipment slot to affect: `hand` (default), `offhand`, `head`, `chest`, `legs`, `feet` | hand    |
| blockdelay             |         | Seconds before the item starts blocking after use                              | 0       |
| disablecooldownscale   |         | Scale factor for the blocking-disabled cooldown (minimum 0)                    | 1       |
| itemdamagethreshold    |         | Damage below this amount doesn't damage the item                               | 0       |
| itemdamagebase         |         | Base durability damage taken per block                                         | 0       |
| itemdamagefactor       |         | Multiplier applied to incoming damage for durability loss                      | 1.5     |
| blocksound             |         | Namespaced sound key played when a hit is blocked                              | none    |
| disabledsound          |         | Namespaced sound key played when blocking is disabled                          | none    |
| bypassedby             |         | Damage-type tag key that bypasses blocking entirely (e.g. `minecraft:bypasses_shield`) | none |
| reductions             |         | `;`-delimited per-damage-type reduction rules — see below                      | none    |

**`reductions=` entry syntax**: `;`-delimited `tagKey:base:factor[:angle]` entries, where `tagKey`
is a damage-type tag key (blank applies to all types), `base`/`factor` are the damage-reduction
formula's constants, and `angle` is an optional horizontal blocking angle in degrees.


## Examples
```yaml
MakeTowerShield:
  Skills:
  - blocksattackscomponent{blockdelay=0.25;itemdamagebase=1;itemdamagefactor=1.0;blocksound="minecraft:item.shield.block";reductions="minecraft:is_explosion:0:0.25;:0:0.5"} @self
```


## Aliases
None.
