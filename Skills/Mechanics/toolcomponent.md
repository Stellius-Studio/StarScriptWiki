## Description
Sets an item's tool mining properties (default mining speed, durability cost per block, whether
it can destroy blocks in Creative), plus optional per-block-type mining speed rules.


## Attributes
| Attribute           | Aliases | Description                                                             | Default |
|---------------------|---------|--------------------------------------------------------------------------------|---------|
| slot                |         | Which equipment slot to affect: `hand` (default), `offhand`, `head`, `chest`, `legs`, `feet` | hand    |
| defaultminingspeed  |         | Mining speed applied to blocks not covered by a rule                           | 1.0     |
| damageperblock      |         | Durability damage taken per block mined                                        | 1       |
| candestroyincreative|         | Whether the item can destroy blocks while in Creative mode                     | true    |
| rules               |         | `;`-delimited per-block-type mining speed rules — see below                    | none    |

**`rules=` entry syntax**: `;`-delimited `blocks:speed:correctfordrops` triples, where `blocks` is
a CSV of block type names, `speed` is a float (or blank to leave the default speed), and
`correctfordrops` is `true`/`false`/blank (unset).


## Examples
```yaml
MakeSpeedPickaxe:
  Skills:
  - toolcomponent{defaultminingspeed=8;damageperblock=1;rules="STONE,COBBLESTONE:12:true;OBSIDIAN::false"} @self
```


## Aliases
None.
