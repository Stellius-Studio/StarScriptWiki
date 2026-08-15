## Description
Fires when a player picks up a dropped item (`EntityPickupItemEvent`, filtered to player pickers
only).


## Config
| Attribute | Description                                                    | Default |
|-----------|-----------------------------------------------------------------------|---------|
| item      | Material filter, comma-separated list allowed (e.g. `DIRT,COBBLESTONE`) | any     |


## Skill Variables
| Variable      | Description                  |
|-----------------|------------------------------------|
| `event-item`     | The picked-up item's material name  |


## Examples
```yaml
Skills:
- message{m="<green>Lucky find!"} @trigger ~onItemPickup{item=CAKE}
```


## See Also
- [itemDrop](Skills-Triggers-itemDrop) — the drop equivalent.
