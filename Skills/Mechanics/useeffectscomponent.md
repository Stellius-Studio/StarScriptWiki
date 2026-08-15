## Description
Sets movement effects applied while using this item, such as drawing a bow/crossbow.


## Attributes
| Attribute            | Aliases | Description                                                              | Default |
|-----------------------|---------|----------------------------------------------------------------------------------|---------|
| slot                  |         | Which equipment slot to affect: `hand` (default), `offhand`, `head`, `chest`, `legs`, `feet` | hand    |
| cansprint             |         | Whether the holder can sprint while using the item                               | false   |
| speedmultiplier       |         | Movement speed multiplier while using, clamped 0.0-1.0                           | 0.2     |
| interactvibrations    |         | Whether using the item emits interaction sculk vibrations                        | true    |


## Examples
```yaml
MakeAgileCrossbow:
  Skills:
  - useeffectscomponent{cansprint=true;speedmultiplier=0.6} @self
```


## Aliases
None.
