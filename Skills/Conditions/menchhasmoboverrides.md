## Description
True if the given mob has any `ApplicableEnchants` overrides defined.


## Attributes
| Attribute | Aliases | Description                                     | Default |
|-----------|---------|------------------------------------------------------|---------|
| mob       |         | The uppercase internal MythicMobs mob name            | none (required) |


## Examples
```yaml
Skills:
- message{m="This mob has custom enchant overrides."} ?menchhasmoboverrides{mob=SKELETON_KING} @trigger
```


## Aliases
None.
