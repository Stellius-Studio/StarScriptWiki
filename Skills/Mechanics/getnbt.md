## Description
Reads one NBT tag from the caster's/target's main-hand item into a skill variable
(`<skill.var.NAME>`).


## Attributes
| Attribute | Aliases | Description                                                                          | Default |
|-----------|---------|-------------------------------------------------------------------------------------------|---------|
| key       |         | The NBT tag's name                                                                          | none (required) |
| type      |         | `byte`/`short`/`int`/`long`/`float`/`double`/`string`/`boolean`/`uuid`                      | string  |
| var       |         | The skill-variable name to write the result into                                            | the `key` value |
| custom    |         | `true` reads from StarScript's own custom NBT sub-compound instead of the item's real vanilla components | false |


## Examples
```yaml
Skills:
- getnbt{key=owner;type=string;var=itemOwner} @trigger
- message{m="Owner: <skill.var.itemOwner>"} @trigger
```


## Aliases
None.
