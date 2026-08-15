## Description
Sets one line (1-15) of the caster's/target's per-player sidebar. Lines beyond the current
length are padded with blank lines automatically. Targets the caster if it's a player,
otherwise the skill's entity target.


## Attributes
| Attribute | Aliases | Description                        | Default |
|-----------|---------|------------------------------------------|---------|
| line      |         | The line number, `1`-`15`                   | none (required) |
| text      |         | The line's text, in MiniMessage format      | none (required) |


## Examples
```yaml
Skills:
- setboardline{line=1;text="<gray>Rank: <yellow>VIP"} @trigger
- setboardline{line=2;text="<gray>Kills: <yellow><skill.var.kills>"} @trigger
```


## Aliases
None.
