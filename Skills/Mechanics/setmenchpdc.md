## Description
Writes a plugin-namespaced PDC value onto the caster's or targeted entity's item, via
MythicEnchants' generic item-PDC helpers — a MythicEnchants-owned namespace, distinct from
StarScript's own storage system, useful for scripts that need to read/write state another
MythicEnchants-aware plugin/addon might also read.


## Attributes
| Attribute | Aliases | Description                                                                     | Default |
|-----------|---------|------------------------------------------------------------------------------------|---------|
| key       |         | The PDC key                                                                        | none (required) |
| value     |         | The value to write                                                                 | none (required) |
| type      |         | The value's type — `string`, `int`, `double`, or `boolean`                         | string |
| slot      |         | Which equipment slot's item to modify — `hand`, `offhand`, `head`, `chest`, `legs`, `feet` | hand |


## Examples
```yaml
Skills:
- setmenchpdc{key=owner;value=<trigger.name>} @trigger
```

```yaml
Skills:
- setmenchpdc{key=charges;value=10;type=int;slot=offhand} @trigger
```


## Aliases
None.
