## Description
Writes one NBT tag on the caster's/target's main-hand item.


## Attributes
| Attribute | Aliases | Description                                                                        | Default |
|-----------|---------|-------------------------------------------------------------------------------------------|---------|
| key       |         | The NBT tag's name                                                                          | none (required) |
| value     |         | The value to write (parsed according to `type=`)                                            | none (required) |
| type      |         | `byte`/`short`/`int`/`long`/`float`/`double`/`string`/`boolean`/`uuid`                      | string  |
| custom    |         | `true` writes into StarScript's own custom NBT sub-compound instead of the item's real vanilla components | false |


## Examples
```yaml
Skills:
- setnbt{key=owner;value="<trigger.name>";type=string} @trigger
```

```yaml
Skills:
- setnbt{key=charge;value=5;type=int;custom=true} @trigger
```


## Aliases
None.
