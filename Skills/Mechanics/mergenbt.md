## Description
Merges a full raw NBT compound string (SNBT syntax, e.g.
`{CustomModelData:5,display:{Name:"foo"}}`) into the caster's/target's main-hand item. Use
this instead of `setnbt` when you need to write more than one tag, or nested/list values, in
a single mechanic call.


## Attributes
| Attribute | Aliases | Description                                                                          | Default |
|-----------|---------|-------------------------------------------------------------------------------------------|---------|
| compound  |         | The NBT compound, in SNBT string syntax                                                     | none (required) |
| custom    |         | `true` merges into StarScript's own custom NBT sub-compound instead of the item's real vanilla components | false |


## Examples
```yaml
Skills:
- mergenbt{compound="{CustomModelData:5,display:{Name:'\"Special Sword\"'}}"} @trigger
```


## Aliases
None.
