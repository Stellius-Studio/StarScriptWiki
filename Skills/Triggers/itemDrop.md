## Description
Fires when a player drops an item (`PlayerDropItemEvent`).


## Config
| Attribute | Description                                                    | Default |
|-----------|-----------------------------------------------------------------------|---------|
| item      | Material filter, comma-separated list allowed (e.g. `DIRT,COBBLESTONE`) | any     |


## Skill Variables
| Variable      | Description                    |
|-----------------|--------------------------------------|
| `event-item`     | The dropped item's material name      |


## Examples
```yaml
Skills:
- message{m="<gray>Don't drop your diamonds!"} @trigger ~onItemDrop{item=DIAMOND}
```


## See Also
- [itemPickup](Skills-Triggers-itemPickup) — the pickup equivalent.
