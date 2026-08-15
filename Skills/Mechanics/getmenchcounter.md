## Description
Reads a MythicEnchants counter value into a skill variable.


## Attributes
| Attribute | Aliases | Description                                                                | Default |
|-----------|---------|------------------------------------------------------------------------------|---------|
| key       |         | The counter's key                                                            | none (required) |
| scope     |         | Where the counter lives — `player` or `item`                                 | player |
| slot      |         | Which equipment slot's item to read the counter from (`scope=item` only) — `hand`, `offhand`, `head`, `chest`, `legs`, `feet` | hand |
| var       |         | The skill variable name to store the counter's value into                    | the `key` value |


## Examples
```yaml
Skills:
- getmenchcounter{key=kills;var=killCount} @trigger
- message{m="Kills: <skill.var.killCount>"} @trigger
```

```yaml
Skills:
- getmenchcounter{key=uses;scope=item;slot=hand} @trigger
```


## Aliases
None.
