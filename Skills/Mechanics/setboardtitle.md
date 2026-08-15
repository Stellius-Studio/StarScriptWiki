## Description
Sets the caster's/target's per-player sidebar (scoreboard) title. Targets the caster if it's
a player, otherwise the skill's entity target.


## Attributes
| Attribute | Aliases | Description                          | Default |
|-----------|---------|-------------------------------------------|---------|
| title     |         | The sidebar's title, in MiniMessage format   | none (required) |


## Examples
```yaml
Skills:
- setboardtitle{title="<gold><bold>My Server"} @trigger
```


## Aliases
None.
