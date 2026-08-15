## Description
Fires when lightning strikes (`LightningStrikeEvent`). The target is the strike location.


## Config
| Attribute | Description                                                    | Default |
|-----------|---------------------------------------------------------------------|---------|
| cause     | Only fire if the strike cause matches (e.g. `TRIDENT`, `WEATHER`, `SPAWNER`) | any     |


## Skill Variables
| Variable      | Description               |
|-----------------|--------------------------------|
| `event-cause`     | The lightning strike's cause name |


## Examples
```yaml
Skills:
- message{m="<yellow>Lightning struck!"} @trigger ~onLightning
```
