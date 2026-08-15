## Description
True if the given enchant id has a configured migration target (`migrations.yml`).


## Attributes
| Attribute | Aliases | Description                 | Default |
|-----------|---------|--------------------------------|---------|
| enchant   |         | The (old) enchantment's namespaced id | none (required) |


## Examples
```yaml
Skills:
- getmenchmigrationtarget{enchant=mythicenchants:old_fire_slash;var=newId} ?ismenchmigrated{enchant=mythicenchants:old_fire_slash} @trigger
```


## Aliases
None.
