## Description
Resizes and/or repositions a world border (defaults to the caster's world).


## Attributes
| Attribute       | Aliases | Description                                                  | Default |
|-----------------|---------|--------------------------------------------------------------|---------|
| world           |         | The name of the world to modify                              | the caster's/target's world |
| size            |         | The new border size (diameter, in blocks)                    | unchanged |
| duration        |         | Ticks over which to gradually resize to `size=` (`0` = instant) | 0       |
| centerx         |         | New border center X coordinate (requires `centerz=` too)     | unchanged |
| centerz         |         | New border center Z coordinate (requires `centerx=` too)     | unchanged |
| warningdistance |         | Distance (blocks) from the border at which the red warning overlay appears | unchanged |
| warningtime     |         | Time (seconds) before border movement at which the warning appears | unchanged |
| damageamount    |         | Damage per second dealt to players outside the border         | unchanged |
| damagebuffer    |         | Distance (blocks) outside the border before damage starts     | unchanged |


## Examples
```yaml
ShrinkBorder:
  Skills:
  - worldborder{size=500;duration=200} @trigger
```
> Gradually shrinks the world border to 500 blocks over 200 ticks (10 seconds).

```yaml
RecenterBorder:
  Skills:
  - worldborder{centerx=0;centerz=0} @trigger
```


## Aliases
None.
