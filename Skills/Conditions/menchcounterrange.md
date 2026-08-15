## Description
True if a MythicEnchants counter's current value matches a range expression.


## Attributes
| Attribute | Aliases | Description                                                                | Default |
|-----------|---------|------------------------------------------------------------------------------|---------|
| key       |         | The counter's key                                                            | none (required) |
| range     |         | The range expression to match — `5`, `>4`, `>=5`, `<10`, `<=9`, `5-10`, `5to10` | none (required) |
| scope     |         | Where the counter lives — `player` or `item`                                 | player |
| slot      |         | Which equipment slot's item to read the counter from (`scope=item` only) — `hand`, `offhand`, `head`, `chest`, `legs`, `feet` | hand |


## Examples
```yaml
Skills:
- message{m="You've reached 10+ kills!"} ?menchcounterrange{key=kills;range=>=10} @trigger
```

```yaml
Skills:
- message{m="This item still has charges."} ?menchcounterrange{key=charges;range=1-99;scope=item;slot=hand} @trigger
```


## Aliases
None.
