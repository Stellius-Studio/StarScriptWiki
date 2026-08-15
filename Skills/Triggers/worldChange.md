## Description
Fires when a player changes worlds (`PlayerChangedWorldEvent`).


## Config
| Attribute | Description                                 | Default |
|-----------|--------------------------------------------------|---------|
| from      | Only fire if leaving this world name                 | any     |
| to        | Only fire if entering this world name                | any     |


## Skill Variables
| Variable            | Description                     |
|-----------------------|--------------------------------------|
| `event-from-world`     | The name of the world the player left |


## Examples
```yaml
Skills:
- message{m="<aqua>Welcome to the Nether!"} @trigger ~onWorldChange{to=world_nether}
```


## See Also
- [portal](Skills-Triggers-portal) — fires specifically for portal-caused world travel, with the teleport cause.
