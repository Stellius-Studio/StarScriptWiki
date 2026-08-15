## Description
Reads the id an enchant is migrated to into a skill variable. Writes an empty string if
`enchant=` has no configured migration.


## Attributes
| Attribute | Aliases | Description                                                    | Default |
|-----------|---------|--------------------------------------------------------------------|---------|
| enchant   |         | The (old) enchantment's namespaced id                              | none (required) |
| var       |         | The skill variable name to store the migration target id into      | migrationtarget |


## Examples
```yaml
Skills:
- getmenchmigrationtarget{enchant=mythicenchants:old_fire_slash;var=newId} @trigger
- message{m="Migrated to: <skill.var.newId>"} @trigger
```


## Aliases
None.
