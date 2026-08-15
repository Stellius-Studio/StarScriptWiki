## Description
Sets a crossbow item's charged/loaded projectiles.


## Attributes
| Attribute | Aliases | Description                                                              | Default |
|-----------|---------|----------------------------------------------------------------------------------|---------|
| slot      |         | Which equipment slot to affect: `hand` (default), `offhand`, `head`, `chest`, `legs`, `feet` | hand    |
| items     |         | CSV of material names to load as charged projectiles (e.g. `ARROW,FIREWORK_ROCKET`) | none (required) |


## Examples
```yaml
PreloadCrossbow:
  Skills:
  - setchargedprojectiles{items="ARROW"} @self
```


## Aliases
None.
