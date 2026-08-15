## Description
Reads the MythicMobs internal type id backing the caster's or targeted entity's item into a skill
variable. Writes an empty string if it isn't a Mythic item, or MythicMobs is unavailable.


## Attributes
| Attribute | Aliases | Description                                                                     | Default |
|-----------|---------|------------------------------------------------------------------------------------|---------|
| slot      |         | Which equipment slot's item to read — `hand`, `offhand`, `head`, `chest`, `legs`, `feet` | hand |
| var       |         | The skill variable name to store the type id into                                  | mythicitemtype |


## Examples
```yaml
Skills:
- getmenchmythicitemtype{var=itemType} @trigger
- message{m="Mythic type: <skill.var.itemType>"} @trigger
```


## Aliases
None.
