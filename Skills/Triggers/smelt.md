## Description
Fires when a furnace (or smoker/blast furnace) smelts an item (`FurnaceSmeltEvent`). The target
location is the furnace block.


## Config
| Attribute | Description                                       | Default |
|-----------|-----------------------------------------------------|---------|
| item      | Only fire if the smelting result matches this material name | any     |


## Skill Variables
| Variable      | Description                     |
|-----------------|---------------------------------------|
| `event-item`      | The smelting result's material name       |


## Examples
```yaml
Skills:
- message{m="<gold>Smelted!"} @trigger ~onSmelt{item=IRON_INGOT}
```


## See Also
- [furnaceExtract](Skills-Triggers-furnaceExtract) — fires when the smelted item is taken out.
