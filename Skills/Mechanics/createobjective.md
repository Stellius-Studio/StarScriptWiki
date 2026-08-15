## Description
Registers a new scoreboard objective. If an objective with the given id already exists, it's
returned unmodified (except for `slot=`, which is still applied).


## Attributes
| Attribute    | Aliases | Description                                                       | Default |
|--------------|---------|-------------------------------------------------------------------------|---------|
| id           |         | The objective's id                                                        | none (required) |
| criteria     |         | The scoring criteria name (e.g. `dummy`, `deathCount`, `playerKillCount`)  | dummy |
| displayname  |         | The objective's display name (MiniMessage)                               | the `id` value |
| rendertype   |         | `integer` or `hearts`                                                    | the criteria's own default |
| slot         |         | A `DisplaySlot` name (e.g. `SIDEBAR`, `BELOW_NAME`, `PLAYER_LIST`)        | not shown |


## Examples
```yaml
Skills:
- createobjective{id=kills;criteria=playerKillCount;displayname="<red>Kills";slot=SIDEBAR}
```


## Aliases
None.
