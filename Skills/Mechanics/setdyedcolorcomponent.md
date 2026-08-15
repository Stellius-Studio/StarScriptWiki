## Description
Sets a dyeable item's (leather armor, etc.) color via the modern data-component API.


## Attributes
| Attribute | Aliases | Description                                                              | Default |
|-----------|---------|----------------------------------------------------------------------------------|---------|
| slot      |         | Which equipment slot to affect: `hand` (default), `offhand`, `head`, `chest`, `legs`, `feet` | hand    |
| color     |         | Hex color (`RRGGBB`)                                                             | FFFFFF (required) |


## Examples
```yaml
DyeLeatherArmorPurple:
  Skills:
  - setdyedcolorcomponent{slot=chest;color="8A2BE2"} @self
```


## Aliases
None.
