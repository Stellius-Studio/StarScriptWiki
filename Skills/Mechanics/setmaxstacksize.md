## Description
Sets an item's maximum stack size.


## Attributes
| Attribute | Aliases | Description                                                              | Default |
|-----------|---------|----------------------------------------------------------------------------------|---------|
| slot      |         | Which equipment slot to affect: `hand` (default), `offhand`, `head`, `chest`, `legs`, `feet` | hand    |
| amount    |         | Max stack size, clamped 1-99                                                     | 64 (required) |


## Examples
```yaml
MakeUnstackableRelic:
  Skills:
  - setmaxstacksize{amount=1} @self
```


## Aliases
None.
