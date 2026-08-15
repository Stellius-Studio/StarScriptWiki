## Description
Fires when a player respawns (`PlayerRespawnEvent`).


## Config
| Attribute | Description                                        | Default |
|-----------|---------------------------------------------------------|---------|
| anchor    | Only fire if respawning via a respawn anchor               | false   |
| bed       | Only fire if respawning via a bed                          | false   |


## Skill Variables
None.


## Examples
```yaml
Skills:
- heal{amount=100} @trigger ~onRespawn
```

```yaml
# Only heals on a bed respawn, not an anchor or default world-spawn respawn.
Skills:
- message{m="<green>You feel well-rested."} @trigger ~onRespawn{bed=true}
```
