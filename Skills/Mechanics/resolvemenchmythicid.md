## Description
Resolves a `mythic:<id>` reference (or a bare MythicMobs item id) to its backing vanilla material
name, into a skill variable. Writes an empty string if unresolvable.


## Attributes
| Attribute | Aliases | Description                                                    | Default |
|-----------|---------|--------------------------------------------------------------------|---------|
| id        |         | The MythicMobs item id, or `mythic:` reference, to resolve         | none (required) |
| var       |         | The skill variable name to store the resolved material name into   | material |


## Examples
```yaml
Skills:
- resolvemenchmythicid{id=mythic:cursebreaker_blade;var=mat} @trigger
- message{m="Backing material: <skill.var.mat>"} @trigger
```


## Aliases
None.
