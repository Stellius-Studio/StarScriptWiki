## Description
True if the caster's item is marked with the vanilla Curse of Vanishing by MythicEnchants' own
tracking (see [setmenchvanillavanishingcurse](Skills-Mechanics-setmenchvanillavanishingcurse)).


## Attributes
| Attribute | Aliases | Description                                                                | Default |
|-----------|---------|------------------------------------------------------------------------------|---------|
| slot      |         | Which equipment slot's item to check — `hand`, `offhand`, `head`, `chest`, `legs`, `feet` | hand |


## Examples
```yaml
Skills:
- message{m="This item will vanish on death!"} ?hasmenchvanillavanishingcurse{} @trigger
```


## Aliases
None.
