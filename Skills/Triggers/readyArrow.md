## Description
Fires when a player readies (nocks) an arrow on a bow/crossbow (`PlayerReadyArrowEvent`).


## Config
None.


## Skill Variables
| Variable      | Description                    |
|-----------------|-------------------------------------|
| `event-arrow`     | The material name of the arrow readied |


## Examples
```yaml
Skills:
- message{m="<aqua>Arrow ready!"} @trigger ~onReadyArrow
```
