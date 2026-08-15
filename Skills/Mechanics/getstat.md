## Description
Reads a player's vanilla statistic into a skill variable (`<skill.var.NAME>`), so it can be
compared with MythicMobs' own `CompareValues` condition. Targets the caster if it's a player,
otherwise the skill's entity target.


## Attributes
| Attribute  | Aliases | Description                                                          | Default            |
|------------|---------|-----------------------------------------------------------------------|---------------------|
| stat       |         | The `Statistic` enum name                                             | none (required)     |
| qualifier  |         | Material or entity type name, as `setstat`                            | none                |
| var        |         | The skill-variable name to write the result into                      | the `stat` value    |


## Examples
```yaml
Skills:
- getstat{stat=PLAYER_KILLS;var=kills} @trigger
- message{m="Kills: <skill.var.kills>"} @trigger
```


## Aliases
None.
