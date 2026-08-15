## Description
True if the caster (a player) has been awarded the given criterion of the given advancement,
without necessarily having completed the whole advancement.


## Attributes
| Attribute    | Aliases | Description                                    | Default |
|--------------|---------|---------------------------------------------------|---------|
| advancement  |         | The advancement's namespaced key                   | none (required) |
| criteria     |         | The criterion name to check                        | none (required) |


## Examples
```yaml
Skills:
- message{m="You've got stone!"} ?hasadvancementcriteria{advancement=minecraft:story/mine_stone;criteria=get_stone} @trigger
```


## Aliases
None.
