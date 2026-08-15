## Description
Sets the minimum attack "charge" (windup fraction) needed before this item deals a
fully-charged attack (mace-style).


## Attributes
| Attribute | Aliases | Description                                                              | Default |
|-----------|---------|----------------------------------------------------------------------------------|---------|
| slot      |         | Which equipment slot to affect: `hand` (default), `offhand`, `head`, `chest`, `legs`, `feet` | hand    |
| charge    |         | Minimum charge fraction needed, clamped 0.0-1.0                                  | 1.0     |


## Examples
```yaml
MakeQuickChargeMace:
  Skills:
  - setminattackcharge{charge=0.5} @self
```


## Aliases
None.
