## Description
Sets which blocks an item is allowed to place on or break while its holder is in Adventure mode.


## Attributes
| Attribute | Aliases | Description                                                              | Default |
|-----------|---------|----------------------------------------------------------------------------------|---------|
| slot      |         | Which equipment slot to affect: `hand` (default), `offhand`, `head`, `chest`, `legs`, `feet` | hand    |
| mode      |         | `place` or `break` — which Adventure-mode predicate to set                       | break   |
| blocks    |         | CSV of block material names this item is allowed to affect                       | none (required) |


## Examples
```yaml
RestrictAdventureBreaking:
  Skills:
  - adventurepredicate{mode=break;blocks="STONE,COBBLESTONE,DEEPSLATE"} @self
```


## Aliases
None.
