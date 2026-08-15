## Description
Sets, adds to, or removes from an item's anvil repair cost (the "Prior Work Penalty").


## Attributes
| Attribute | Aliases | Description                                                              | Default |
|-----------|---------|----------------------------------------------------------------------------------|---------|
| slot      |         | Which equipment slot to affect: `hand` (default), `offhand`, `head`, `chest`, `legs`, `feet` | hand    |
| amount    |         | Amount to set/add/remove                                                         | 0 (required) |
| mode      |         | `set`, `add`, or `remove`                                                        | set     |

The resulting repair cost is never allowed to go below 0.


## Examples
```yaml
ResetRepairCost:
  Skills:
  - repaircost{amount=0;mode=set} @self
```

```yaml
PenalizeRepair:
  Skills:
  - repaircost{amount=1;mode=add} @self
```


## Aliases
None.
