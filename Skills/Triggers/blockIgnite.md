## Description
Fires when a block catches fire (`BlockIgniteEvent`). Fires with a player context if a player
caused it, otherwise a location-only context. The target location is the ignited block.


## Config
| Attribute | Description                                                       | Default |
|-----------|------------------------------------------------------------------------|---------|
| cause     | Only fire if the ignition cause matches (e.g. `FLINT_AND_STEEL`, `LAVA`, `LIGHTNING`) | any     |


## Skill Variables
| Variable      | Description                 |
|-----------------|----------------------------------|
| `event-cause`     | The ignition cause name           |


## Examples
```yaml
Skills:
- message{m="<red>Fire started!"} @trigger ~onBlockIgnite
```
