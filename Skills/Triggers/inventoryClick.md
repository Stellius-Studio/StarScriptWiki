## Description
Fires when a player clicks a slot in an open inventory (`InventoryClickEvent`).


## Config
| Attribute | Description                                                | Default |
|-----------|-----------------------------------------------------------------|---------|
| type      | Only fire if the inventory type matches                          | any     |
| click     | Only fire if the click type matches (e.g. `LEFT`, `RIGHT`, `SHIFT_LEFT`) | any     |
| slot      | Only fire if the clicked slot index matches                       | any     |
| item      | Only fire if the clicked slot's item matches this material name    | any     |


## Skill Variables
| Variable      | Description                          |
|-----------------|-------------------------------------------|
| `event-slot`      | The clicked slot index                       |
| `event-click`     | The click type name                          |
| `event-item`      | The clicked slot's item material name (`AIR` if empty) |


## Examples
```yaml
Skills:
- message{m="<aqua>Clicked slot <skill.var.event-slot>"} @trigger ~onInventoryClick
```
