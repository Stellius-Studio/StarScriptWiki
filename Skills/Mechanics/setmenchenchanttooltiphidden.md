## Description
Hides or shows the caster's or targeted entity's item's real enchantment tooltip.


## Attributes
| Attribute | Aliases | Description                                                                     | Default |
|-----------|---------|------------------------------------------------------------------------------------|---------|
| hidden    |         | Whether the real enchantment tooltip should be hidden                              | true |
| slot      |         | Which equipment slot's item to modify — `hand`, `offhand`, `head`, `chest`, `legs`, `feet` | hand |


## Examples
```yaml
Skills:
- setmenchenchanttooltiphidden{hidden=true} @trigger
```

```yaml
Skills:
- setmenchenchanttooltiphidden{hidden=false;slot=head} @trigger
```


## Aliases
None.
