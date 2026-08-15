## Description
Sets, adds to, subtracts from, or resets a player's vanilla statistic. Targets the caster if
it's a player, otherwise the skill's entity target (if a player).


## Attributes
| Attribute  | Aliases | Description                                                                                   | Default |
|------------|---------|-------------------------------------------------------------------------------------------------|---------|
| stat       |         | The `Statistic` enum name (e.g. `MINE_BLOCK`, `PLAYER_KILLS`, `JUMP`)                           | none (required) |
| qualifier  |         | Material or entity type name — required for block/item/entity-typed statistics, ignored otherwise | none |
| value      |         | The value to set/add/remove                                                                     | 0       |
| mode       |         | `set`, `add`, `remove`, or `reset`                                                               | set     |


## Examples
```yaml
Skills:
- setstat{stat=PLAYER_KILLS;mode=add;value=1} @trigger
```

```yaml
Skills:
- setstat{stat=MINE_BLOCK;qualifier=DIAMOND_ORE;mode=reset} @trigger
```


## Aliases
None.
