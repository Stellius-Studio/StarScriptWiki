## Description
True if the caster (a player) has completed the given advancement.


## Attributes
| Attribute    | Aliases | Description                                                        | Default |
|--------------|---------|------------------------------------------------------------------------|---------|
| advancement  |         | The advancement's namespaced key (e.g. `minecraft:story/mine_stone`)   | none (required) |


## Examples
```yaml
Skills:
- message{m="You've mined stone before!"} ?hasadvancement{advancement=minecraft:story/mine_stone} @trigger
```


## Aliases
None.
