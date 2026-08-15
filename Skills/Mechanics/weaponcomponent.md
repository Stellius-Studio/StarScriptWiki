## Description
Sets an item's melee-weapon properties: durability cost per attack and how long it disables
shield blocking on hit.


## Attributes
| Attribute       | Aliases | Description                                                              | Default |
|-----------------|---------|---------------------------------------------------------------------------------|---------|
| slot            |         | Which equipment slot to affect: `hand` (default), `offhand`, `head`, `chest`, `legs`, `feet` | hand    |
| itemdamage      |         | Durability damage taken per attack (minimum 0)                                  | 1       |
| disableblocking |         | Seconds a shield block is disabled for when hit by this weapon                  | 0       |


## Examples
```yaml
MakeShieldBreakerSword:
  Skills:
  - weaponcomponent{itemdamage=2;disableblocking=3.0} @self
```


## Aliases
None.
