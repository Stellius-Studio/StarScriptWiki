## Description
Marks or unmarks an item as an elytra-like glider (a flag-only component with no other fields).


## Attributes
| Attribute | Aliases | Description                                                              | Default |
|-----------|---------|----------------------------------------------------------------------------------|---------|
| slot      |         | Which equipment slot to affect: `hand` (default), `offhand`, `head`, `chest`, `legs`, `feet` | hand    |
| state     |         | `true` marks the item as a glider, `false` clears it                             | true    |


## Examples
```yaml
MakeCustomElytra:
  Skills:
  - setglidercomponent{slot=chest} @self
```


## Aliases
None.
