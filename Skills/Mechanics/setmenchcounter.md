## Description
Overwrites a MythicEnchants counter to exactly `value=`. Setting it to `0` removes the counter
entirely.


## Attributes
| Attribute | Aliases | Description                                                                | Default |
|-----------|---------|------------------------------------------------------------------------------|---------|
| key       |         | The counter's key                                                            | none (required) |
| value     |         | The exact value to set (`0` removes the counter)                             | none (required) |
| duration  |         | How long until the counter expires — `<n>t`/`<n>s`/`never` grammar           | never |
| scope     |         | Where the counter lives — `player` or `item`                                 | player |
| slot      |         | Which equipment slot's item to store the counter on (`scope=item` only) — `hand`, `offhand`, `head`, `chest`, `legs`, `feet` | hand |


## Examples
```yaml
Skills:
- setmenchcounter{key=kills;value=0} @trigger
```

```yaml
Skills:
- setmenchcounter{key=charges;value=5;scope=item;slot=offhand;duration=1200s} @trigger
```


## Aliases
None.
