## Description
True if the caster's main-hand item has the given NBT tag set.


## Attributes
| Attribute | Aliases | Description                                                                        | Default |
|-----------|---------|-------------------------------------------------------------------------------------------|---------|
| key       |         | The NBT tag's name                                                                          | none (required) |
| custom    |         | `true` checks StarScript's own custom NBT sub-compound instead of the item's real vanilla components | false |


## Examples
```yaml
Skills:
- message{m="This item has an owner tag."} ?hasnbttag{key=owner} @trigger
```


## Aliases
None.
