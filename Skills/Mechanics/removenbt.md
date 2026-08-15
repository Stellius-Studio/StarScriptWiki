## Description
Removes one NBT tag from the caster's/target's main-hand item.


## Attributes
| Attribute | Aliases | Description                                                                        | Default |
|-----------|---------|-------------------------------------------------------------------------------------------|---------|
| key       |         | The NBT tag's name                                                                          | none (required) |
| custom    |         | `true` removes from StarScript's own custom NBT sub-compound instead of the item's real vanilla components | false |


## Examples
```yaml
Skills:
- removenbt{key=owner} @trigger
```


## Aliases
None.
