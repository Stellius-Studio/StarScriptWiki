## Description
Loads an already-existing world by name, or generates a brand-new one if no world by that name
exists yet on disk. A no-op (successful) if the named world is already loaded.


## Attributes
| Attribute   | Aliases | Description                                                    | Default |
|-------------|---------|---------------------------------------------------------------|---------|
| name        |         | The world's name                                               | none (required) |
| seed        |         | World seed. Numeric strings are parsed as a `long`; non-numeric strings are hashed the same way vanilla hashes text seeds | random  |
| type        |         | World type (e.g. `NORMAL`, `FLAT`, `AMPLIFIED`)                 | server default |
| generator   |         | Name of a custom chunk generator plugin to use                 | vanilla |
| environment |         | World environment (`NORMAL`, `NETHER`, `THE_END`)               | NORMAL  |


## Examples
```yaml
LoadArenaWorld:
  Skills:
  - worldload{name=arena_world} @trigger
```

```yaml
GenerateFlatWorld:
  Skills:
  - worldload{name=flat_test;type=FLAT;environment=NORMAL} @trigger
```


## Aliases
None.
