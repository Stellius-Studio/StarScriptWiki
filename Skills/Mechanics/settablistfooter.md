## Description
Sets the caster's/target's tablist footer, leaving the header unchanged.


## Attributes
| Attribute | Aliases | Description                                                   | Default |
|-----------|---------|---------------------------------------------------------------------|---------|
| text      |         | The footer text, in MiniMessage format                                | none (required) |
| persist   |         | `true` reapplies this footer on the player's next join                | false   |


## Examples
```yaml
Skills:
- settablistfooter{text="<gray>play.example.com"} @trigger ~onJoin
```


## Aliases
None.
