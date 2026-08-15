## Description
True if the caster's item is marked with the vanilla Curse of Binding by MythicEnchants' own
tracking (see [setmenchvanillabindingcurse](Skills-Mechanics-setmenchvanillabindingcurse)).


## Attributes
| Attribute | Aliases | Description                                                                | Default |
|-----------|---------|------------------------------------------------------------------------------|---------|
| slot      |         | Which equipment slot's item to check — `hand`, `offhand`, `head`, `chest`, `legs`, `feet` | hand |


## Examples
```yaml
Skills:
- message{m="This item is bound to you!"} ?hasmenchvanillabindingcurse{slot=head} @trigger
```


## Aliases
None.
