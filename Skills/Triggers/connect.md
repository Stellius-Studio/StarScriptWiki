## Description
Fires when a player logs in (`PlayerLoginEvent`), before they spawn into the world.


## Config
None.


## Skill Variables
| Variable          | Description                     |
|--------------------|----------------------------------|
| `event-hostname`   | The hostname the player connected through |


## Examples
```yaml
Skills:
- message{m="<aqua>Welcome!"} @trigger ~onConnect
```
