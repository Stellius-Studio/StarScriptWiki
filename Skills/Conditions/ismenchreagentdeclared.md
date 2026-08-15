## Description
True if the given key has a declared MythicEnchants reagent definition (from `reagents/` or a
pack overlay).


## Attributes
| Attribute | Aliases | Description        | Default |
|-----------|---------|-------------------------|---------|
| key       |         | The reagent key to check | none (required) |


## Examples
```yaml
Skills:
- message{m="Unknown reagent key!"} ?ismenchreagentdeclared{key=lapis_dust;NOT} @trigger
```


## Aliases
None.
