## Description
Serializes every enchantment on the caster's or targeted entity's item into a skill variable, as
`id:level,id:level,...`. Pair with [restoremenchenchants](Skills-Mechanics-restoremenchenchants)
to restore the snapshot onto an item later.


## Attributes
| Attribute | Aliases | Description                                                                     | Default |
|-----------|---------|------------------------------------------------------------------------------------|---------|
| var       |         | The skill variable name to store the serialized snapshot into                      | none (required) |
| slot      |         | Which equipment slot's item to read — `hand`, `offhand`, `head`, `chest`, `legs`, `feet` | hand |


## Examples
```yaml
Skills:
- snapshotmenchenchants{var=savedEnchants} @trigger
- message{m="Snapshot: <skill.var.savedEnchants>"} @trigger
```


## Aliases
None.
