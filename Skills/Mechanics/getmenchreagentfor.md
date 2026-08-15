## Description
Reads the reagent key the caster's or targeted entity's item would match at the custom enchanting
table into a skill variable. Writes an empty string if it matches no declared reagent.


## Attributes
| Attribute | Aliases | Description                                                                     | Default |
|-----------|---------|------------------------------------------------------------------------------------|---------|
| slot      |         | Which equipment slot's item to read — `hand`, `offhand`, `head`, `chest`, `legs`, `feet` | hand |
| var       |         | The skill variable name to store the reagent key into                              | reagentkey |


## Examples
```yaml
Skills:
- getmenchreagentfor{var=matchedReagent} @trigger
- message{m="Matches reagent: <skill.var.matchedReagent>"} @trigger
```


## Aliases
None.
