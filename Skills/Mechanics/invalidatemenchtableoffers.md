## Description
Forces the caster's or targeted entity's cached MythicEnchants table offers to be dropped, so the
next `PrepareItemEnchantEvent` recomputes them from scratch.


## Attributes
None.


## Examples
```yaml
Skills:
- invalidatemenchtableoffers{} @trigger
```


## Aliases
None.
