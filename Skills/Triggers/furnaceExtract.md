## Description
Fires when a player takes smelted items out of a furnace (`FurnaceExtractEvent`).


## Config
| Attribute | Description                                       | Default |
|-----------|-----------------------------------------------------|---------|
| item      | Only fire if the extracted item matches this material name | any     |


## Skill Variables
| Variable       | Description                     |
|------------------|---------------------------------------|
| `event-item`       | The extracted item's material name        |
| `event-amount`     | How many items were extracted               |
| `event-exp`        | How much experience was granted             |


## Examples
```yaml
Skills:
- message{m="<gold>Collected smelted goods!"} @trigger ~onFurnaceExtract
```


## See Also
- [smelt](Skills-Triggers-smelt) — fires when the item finishes smelting.
