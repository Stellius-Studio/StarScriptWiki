## Description
Fires when a player's equipped armor changes (`PlayerArmorChangeEvent`).


## Config
| Attribute | Description                                          | Default |
|-----------|---------------------------------------------------------|---------|
| slot      | Only fire if the changed slot matches (`HEAD`, `CHEST`, `LEGS`, `FEET`) | any     |


## Skill Variables
| Variable     | Description                     |
|----------------|-------------------------------------|
| `event-slot`     | The name of the armor slot that changed |


## Examples
```yaml
Skills:
- message{m="<aqua>Helmet changed!"} @trigger ~onArmorChange{slot=HEAD}
```
