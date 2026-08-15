## Description
Overrides the damage type used when this item damages something directly (e.g. a mace-smash
hit). Requires Minecraft 1.21.11+.


## Attributes
| Attribute  | Aliases | Description                                                              | Default |
|------------|---------|----------------------------------------------------------------------------------|---------|
| slot       |         | Which equipment slot to affect: `hand` (default), `offhand`, `head`, `chest`, `legs`, `feet` | hand    |
| damagetype |         | Namespaced damage-type key (e.g. `minecraft:mace_smash`)                         | none (required) |


## Examples
```yaml
MakeCustomDamageWeapon:
  Skills:
  - setdamagetypecomponent{damagetype="minecraft:mace_smash"} @self
```


## Aliases
None.
