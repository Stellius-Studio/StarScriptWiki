## Description
Reads the caster's or targeted entity's item's custom-item source id (e.g. `nexo:purify_scroll`,
`mythic:cursebreaker_dust`) into a skill variable. Writes an empty string if the item isn't a
recognized custom item.


## Attributes
| Attribute | Aliases | Description                                                                     | Default |
|-----------|---------|------------------------------------------------------------------------------------|---------|
| slot      |         | Which equipment slot's item to read — `hand`, `offhand`, `head`, `chest`, `legs`, `feet` | hand |
| var       |         | The skill variable name to store the id into                                       | customitemid |


## Examples
```yaml
Skills:
- getmenchcustomitemid{var=heldId} @trigger
- message{m="Holding: <skill.var.heldId>"} @trigger
```


## Aliases
None.
