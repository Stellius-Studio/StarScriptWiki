## Description
True if the caster's item's real enchantment tooltip is currently hidden (see
[setmenchenchanttooltiphidden](Skills-Mechanics-setmenchenchanttooltiphidden)).


## Attributes
| Attribute | Aliases | Description                                                                | Default |
|-----------|---------|------------------------------------------------------------------------------|---------|
| slot      |         | Which equipment slot's item to check — `hand`, `offhand`, `head`, `chest`, `legs`, `feet` | hand |


## Examples
```yaml
Skills:
- setmenchenchanttooltiphidden{hidden=false} ?ismenchenchanttooltiphidden{} @trigger
```


## Aliases
None.
