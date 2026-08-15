## Description
Sets the caster's/target's tablist header, leaving the footer unchanged.


## Attributes
| Attribute | Aliases | Description                                                   | Default |
|-----------|---------|---------------------------------------------------------------------|---------|
| text      |         | The header text, in MiniMessage format                                | none (required) |
| persist   |         | `true` reapplies this header on the player's next join                | false   |


## Examples
```yaml
Skills:
- settablistheader{text="<gold>My Server"} @trigger ~onJoin
```

```yaml
Skills:
- settablistheader{text="<gold>My Server";persist=true} @trigger ~onJoin
```


## Aliases
None.
