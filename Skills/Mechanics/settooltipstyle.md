## Description
Overrides the resource-pack-defined style key used to render this item's tooltip.


## Attributes
| Attribute | Aliases | Description                                                              | Default |
|-----------|---------|----------------------------------------------------------------------------------|---------|
| slot      |         | Which equipment slot to affect: `hand` (default), `offhand`, `head`, `chest`, `legs`, `feet` | hand    |
| style     |         | Namespaced tooltip style key (e.g. `mynamespace:fancy_tooltip`)                  | none (required) |


## Examples
```yaml
MakeFancyTooltipItem:
  Skills:
  - settooltipstyle{style="mynamespace:fancy_tooltip"} @self
```


## Aliases
None.
