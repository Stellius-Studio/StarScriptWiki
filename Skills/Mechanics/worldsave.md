## Description
Saves a world to disk (defaults to the caster's world), optionally unloading it afterward.


## Attributes
| Attribute | Aliases | Description                                          | Default |
|-----------|---------|-------------------------------------------------------|---------|
| world     |         | The name of the world to save                          | the caster's/target's world |
| unload    |         | If `true`, saves and then unloads the world in one step | false   |


## Examples
```yaml
SaveCurrentWorld:
  Skills:
  - worldsave @trigger
```

```yaml
SaveAndUnload:
  Skills:
  - worldsave{world=temp_world;unload=true} @trigger
```


## Aliases
None.
