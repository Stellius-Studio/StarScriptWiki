## Description
Marks or unmarks a projectile item as intangible (a flag-only component with no other fields).


## Attributes
| Attribute | Aliases | Description                                                              | Default |
|-----------|---------|----------------------------------------------------------------------------------|---------|
| slot      |         | Which equipment slot to affect: `hand` (default), `offhand`, `head`, `chest`, `legs`, `feet` | hand    |
| state     |         | `true` marks the projectile as intangible, `false` clears it                     | true    |


## Examples
```yaml
MakePhantomArrow:
  Skills:
  - setintangibleprojectilecomponent @self
```


## Aliases
None.
