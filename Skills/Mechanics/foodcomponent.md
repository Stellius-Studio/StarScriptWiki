## Description
Sets an item's food properties (nutrition, saturation, and whether it can always be eaten
regardless of hunger).


## Attributes
| Attribute    | Aliases | Description                                                          | Default |
|--------------|---------|-----------------------------------------------------------------------------|---------|
| slot         |         | Which equipment slot to affect: `hand` (default), `offhand`, `head`, `chest`, `legs`, `feet` | hand    |
| nutrition    |         | Hunger points restored on eating                                            | 0 (required) |
| saturation   |         | Saturation restored on eating                                               | 0.0 (required) |
| canalwayseat |         | Whether the item can be eaten even at full hunger                           | false   |


## Examples
```yaml
MakeGoldenApplePlus:
  Skills:
  - foodcomponent{nutrition=8;saturation=12.8;canalwayseat=true} @self
```


## Aliases
None.
