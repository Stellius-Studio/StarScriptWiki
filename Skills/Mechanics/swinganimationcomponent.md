## Description
Sets the arm-swing animation played when this item is used.


## Attributes
| Attribute | Aliases | Description                                                              | Default |
|-----------|---------|----------------------------------------------------------------------------------|---------|
| slot      |         | Which equipment slot to affect: `hand` (default), `offhand`, `head`, `chest`, `legs`, `feet` | hand    |
| type      |         | Animation type: `none`, `whack`, `stab`                                          | whack   |
| duration  |         | Animation duration, in ticks                                                     | 6       |


## Examples
```yaml
MakeStabbyDagger:
  Skills:
  - swinganimationcomponent{type=stab;duration=4} @self
```


## Aliases
None.
