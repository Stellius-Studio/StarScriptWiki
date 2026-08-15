## Description
Fires when a player finishes eating or drinking an item (`PlayerItemConsumeEvent`).


## Config
| Attribute | Description                                                    | Default |
|-----------|-----------------------------------------------------------------------|---------|
| item      | Material filter, comma-separated list allowed (e.g. `GOLDEN_APPLE,POTION`) | any     |


## Skill Variables
| Variable      | Description                    |
|-----------------|--------------------------------------|
| `event-item`     | The consumed item's material name     |


## Examples
```yaml
Skills:
- heal{amount=20} @trigger ~onItemConsume{item=GOLDEN_APPLE}
```
