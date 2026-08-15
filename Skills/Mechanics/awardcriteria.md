## Description
Awards (or revokes) one advancement criterion for a player. Targets the caster if it's a
player, otherwise the skill's entity target.


## Attributes
| Attribute    | Aliases | Description                                                             | Default |
|--------------|---------|---------------------------------------------------------------------------|---------|
| advancement  |         | The advancement's namespaced key (e.g. `minecraft:story/mine_stone`)      | none (required) |
| criteria     |         | The criterion name to award/revoke                                        | none (required) |
| revoke       |         | `true` revokes the criterion instead of awarding it                       | false   |


## Examples
```yaml
Skills:
- awardcriteria{advancement=minecraft:story/mine_stone;criteria=get_stone} @trigger
```


## Aliases
None.
