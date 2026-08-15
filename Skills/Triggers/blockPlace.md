## Description
Fires when a player places a block (`BlockPlaceEvent`). The target is the placed block's
location.


## Config
| Attribute | Description                                                    | Default |
|-----------|-----------------------------------------------------------------------|---------|
| block     | Material filter, comma-separated list allowed (e.g. `TNT,OBSIDIAN`)         | any     |


## Skill Variables
| Variable      | Description                  |
|-----------------|------------------------------------|
| `event-block`    | The placed block's material name    |


## Examples
```yaml
Skills:
- message{m="<red>Placing TNT is not allowed here!"} @trigger ~onBlockPlace{block=TNT}
```


## See Also
- [blockBreak](Skills-Triggers-blockBreak) — the breaking equivalent.
