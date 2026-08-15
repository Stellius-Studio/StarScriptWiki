## Description
Fires when a player's anvil result is calculated (`PrepareAnvilEvent`).


## Config
None.


## Skill Variables
| Variable       | Description                        |
|------------------|------------------------------------------|
| `event-result`     | The prepared result item's material name (`AIR` if no valid result) |


## Examples
```yaml
Skills:
- message{m="<aqua>Anvil result ready"} @trigger ~onAnvilPrepare
```
