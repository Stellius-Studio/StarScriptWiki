## Description
Toggles PvP for a world (defaults to the caster's world).


## Attributes
| Attribute | Aliases | Description                                                  | Default            |
|-----------|---------|------------------------------------------------------------------|---------------------|
| world     |         | The name of the world to toggle PvP in                           | the caster's world  |
| state     |         | `true` to enable PvP, `false` to disable it                      | true                |


## Examples
```yaml
DisablePvpInSpawn:
  Skills:
  - pvp{world=spawn_world;state=false} @trigger
```

```yaml
EnablePvpHere:
  Skills:
  - pvp @trigger
```
> Enables PvP in the caster's current world.


## Aliases
None.
