## Description
Removes a MythicEnchants counter entirely.


## Attributes
| Attribute | Aliases | Description                                                                | Default |
|-----------|---------|------------------------------------------------------------------------------|---------|
| key       |         | The counter's key                                                            | none (required) |
| scope     |         | Where the counter lives — `player` or `item`                                 | player |
| slot      |         | Which equipment slot's item to remove the counter from (`scope=item` only) — `hand`, `offhand`, `head`, `chest`, `legs`, `feet` | hand |


## Examples
```yaml
Skills:
- removemenchcounter{key=kills} @trigger
```

```yaml
Skills:
- removemenchcounter{key=charges;scope=item;slot=hand} @trigger
```


## Aliases
None.
