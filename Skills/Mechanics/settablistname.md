## Description
Sets the caster's/target's own displayed name in the tablist (not the global header/footer).


## Attributes
| Attribute | Aliases | Description                                               | Default |
|-----------|---------|-------------------------------------------------------------------|---------|
| text      |         | The tablist name, in MiniMessage format                             | none (required) |
| persist   |         | `true` reapplies this name on the player's next join                 | false   |


## Examples
```yaml
Skills:
- settablistname{text="<red>[Admin] <white><trigger.name>"} @trigger ~onJoin
```


## Aliases
None.
