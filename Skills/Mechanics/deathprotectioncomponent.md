## Description
Makes an item act like a totem of undying — consumed to prevent death, running the given
consume effects when triggered.


## Attributes
| Attribute | Aliases | Description                                                              | Default |
|-----------|---------|----------------------------------------------------------------------------------|---------|
| slot      |         | Which equipment slot to affect: `hand` (default), `offhand`, `head`, `chest`, `legs`, `feet` | hand    |
| effects   |         | `;`-delimited consume effects run when the death protection triggers — same syntax as [consumablecomponent](Skills-Mechanics-consumablecomponent)'s `effects=` | none |


## Examples
```yaml
MakeCustomTotem:
  Skills:
  - deathprotectioncomponent{effects="apply:regeneration,900,1;apply:absorption,100,1;sound:minecraft:item.totem.use"} @self
```


## Aliases
None.
