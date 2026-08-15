## Description
Hides or shows an item's entire tooltip.


## Attributes
| Attribute | Aliases | Description                                                          | Default |
|-----------|---------|---------------------------------------------------------------------|---------|
| slot      |         | Which equipment slot to affect: `hand` (default), `offhand`, `head`, `chest`, `legs`, `feet` | hand    |
| state     |         | `true` hides the tooltip, `false` shows it                          | true    |


## Examples
```yaml
HideItemTooltip:
  Skills:
  - itemtooltip @self
```

```yaml
ShowItemTooltip:
  Skills:
  - itemtooltip{state=false} @self
```


## Aliases
None.
