## Description
Fires when a player closes an inventory (`InventoryCloseEvent`).


## Config
| Attribute | Description                                          | Default |
|-----------|-----------------------------------------------------------|---------|
| type      | Only fire if the inventory type matches (e.g. `CHEST`, `ANVIL`) | any     |


## Skill Variables
| Variable     | Description             |
|----------------|------------------------------|
| `event-type`     | The inventory type name    |


## Examples
```yaml
Skills:
- message{m="<aqua>Closed a chest!"} @trigger ~onInventoryClose{type=CHEST}
```


## See Also
- [inventoryOpen](Skills-Triggers-inventoryOpen) — the counterpart trigger.
