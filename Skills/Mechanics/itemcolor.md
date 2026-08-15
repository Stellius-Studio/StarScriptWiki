## Description
Recolors leather armor, potions, or maps via a hex `RRGGBB` color. Fails with an invalid-config
result if the targeted item's type doesn't support coloring (e.g. a plain block item).


## Attributes
| Attribute | Aliases | Description                                                        | Default |
|-----------|---------|-------------------------------------------------------------------|---------|
| slot      |         | Which equipment slot to color: `hand` (default), `offhand`, `head`, `chest`, `legs`, `feet` | hand    |
| color     | c       | The hex color to apply, e.g. `FF0000` (with or without a leading `#`) | FFFFFF  |


## Examples
```yaml
RedLeatherArmor:
  Skills:
  - itemcolor{slot=chest;color=FF0000} @self
```

```yaml
BluePotion:
  Skills:
  - itemcolor{color=0000FF} @self
```


## Aliases
- [x] recolor
