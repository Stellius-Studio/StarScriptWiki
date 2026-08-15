## Description
Sets a goat-horn item's played instrument.


## Attributes
| Attribute  | Aliases | Description                                                              | Default |
|------------|---------|----------------------------------------------------------------------------------|---------|
| slot       |         | Which equipment slot to affect: `hand` (default), `offhand`, `head`, `chest`, `legs`, `feet` | hand    |
| instrument |         | Namespaced instrument key (e.g. `minecraft:ponder_goat_horn`)                    | none (required) |


## Examples
```yaml
MakeSeekGoatHorn:
  Skills:
  - instrumentcomponent{instrument="minecraft:seek_goat_horn"} @self
```


## Aliases
None.
