## Description
Restores an item's enchantments from a [snapshotmenchenchants](Skills-Mechanics-snapshotmenchenchants)-produced
`id:level,id:level,...` string, replacing whatever enchantments are currently on the caster's or
targeted entity's item.


## Attributes
| Attribute | Aliases | Description                                                                     | Default |
|-----------|---------|------------------------------------------------------------------------------------|---------|
| snapshot  |         | The serialized snapshot string, e.g. `<skill.var.savedEnchants>`                    | none (required) |
| slot      |         | Which equipment slot's item to modify — `hand`, `offhand`, `head`, `chest`, `legs`, `feet` | hand |


## Examples
```yaml
Skills:
- restoremenchenchants{snapshot=<skill.var.savedEnchants>} @trigger
```


## Aliases
None.
