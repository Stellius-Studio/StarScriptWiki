## Description
True if the given enchant id would be treated as orphaned/stale by MythicEnchants' own cleanup
pass.


## Attributes
| Attribute | Aliases | Description                 | Default |
|-----------|---------|--------------------------------|---------|
| enchant   |         | The enchantment's namespaced id | none (required) |


## Examples
```yaml
Skills:
- message{m="<red>Warning: <skill.var.enchantId> is orphaned."} ?ismenchorphaned{enchant=mythicenchants:removed_enchant} @trigger
```


## Aliases
None.
