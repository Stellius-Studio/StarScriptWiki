## Description
Fires when a dispenser dispenses an item (`BlockDispenseEvent`). The target location is the
dispenser block.


## Config
| Attribute | Description                                       | Default |
|-----------|-----------------------------------------------------|---------|
| item      | Only fire if the dispensed item matches this material name | any     |


## Skill Variables
| Variable      | Description                     |
|-----------------|--------------------------------------|
| `event-item`      | The dispensed item's material name      |


## Examples
```yaml
Skills:
- message{m="<aqua>Dispensed!"} @trigger ~onDispense
```
