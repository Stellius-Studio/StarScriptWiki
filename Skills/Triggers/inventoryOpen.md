## Description
Fires when a player opens an inventory (`InventoryOpenEvent`).


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
- message{m="<aqua>Opened a chest!"} @trigger ~onInventoryOpen{type=CHEST}
```


## See Also
- [inventoryClose](Skills-Triggers-inventoryClose) — the counterpart trigger.
