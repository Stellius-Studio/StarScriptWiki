## Description
Adds `delta=` to a MythicEnchants counter (creating it if unset), refreshing its expiry.


## Attributes
| Attribute | Aliases | Description                                                                | Default |
|-----------|---------|------------------------------------------------------------------------------|---------|
| key       |         | The counter's key                                                            | none (required) |
| delta     |         | The amount to add (may be negative to subtract)                              | 1 |
| duration  |         | How long until the counter expires — `<n>t`/`<n>s`/`never` grammar           | never |
| scope     |         | Where the counter lives — `player` or `item`                                 | player |
| slot      |         | Which equipment slot's item to store the counter on (`scope=item` only) — `hand`, `offhand`, `head`, `chest`, `legs`, `feet` | hand |


## Examples
```yaml
Skills:
- addmenchcounter{key=kills;delta=1} @trigger
```

```yaml
Skills:
- addmenchcounter{key=charges;delta=-1;scope=item;slot=hand;duration=600s} @trigger
```


## Aliases
None.
