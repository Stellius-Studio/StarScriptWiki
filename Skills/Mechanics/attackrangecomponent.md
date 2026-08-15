## Description
Sets an item's melee attack-reach overrides (survival/creative reach, hitbox margin, and the
factor applied when the attacker is a mob).


## Attributes
| Attribute        | Aliases | Description                                                          | Default |
|-------------------|---------|-----------------------------------------------------------------------------|---------|
| slot              |         | Which equipment slot to affect: `hand` (default), `offhand`, `head`, `chest`, `legs`, `feet` | hand    |
| minreach          |         | Minimum survival-mode attack reach, clamped 0-64                            | unset   |
| maxreach          |         | Maximum survival-mode attack reach, clamped 0-64                            | unset   |
| mincreativereach  |         | Minimum Creative-mode attack reach, clamped 0-64                            | unset   |
| maxcreativereach  |         | Maximum Creative-mode attack reach, clamped 0-64                            | unset   |
| hitboxmargin      |         | Extra hitbox margin added to targets, clamped 0-1                           | 0       |
| mobfactor         |         | Reach multiplier applied when a mob wields this item, clamped 0-2           | 1       |


## Examples
```yaml
MakeLongReachSpear:
  Skills:
  - attackrangecomponent{minreach=3;maxreach=6;mobfactor=1.5} @self
```


## Aliases
None.
