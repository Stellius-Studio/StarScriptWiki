## Description
Fires when a player breaks a block (`BlockBreakEvent`). The target is the broken block's
location.


## Config
| Attribute       | Description                                                             | Default |
|-----------------|------------------------------------------------------------------------------|---------|
| block (aliases `blocks`, `b`) | Material filter, comma-separated list allowed (e.g. `DIAMOND_ORE,DEEPSLATE_DIAMOND_ORE`) | any     |


## Skill Variables
| Variable      | Description                  |
|-----------------|------------------------------------|
| `event-block`    | The broken block's material name    |


## Examples
```yaml
OreAlert:
  Cooldown: 5
  Skills:
  - message{m="<aqua>You mined <skill.var.event-block>!"} @trigger ~onBlockBreak{block=DIAMOND_ORE,DEEPSLATE_DIAMOND_ORE}
  - sound{s=entity.player.levelup;volume=1;pitch=1.5} @trigger
```


## See Also
- [blockPlace](Skills-Triggers-blockPlace) — the placement equivalent.
