## Description
True if the caster is currently pressing the given movement input key.


## Attributes
| Attribute | Aliases | Description                                                        | Default |
|-----------|---------|---------------------------------------------------------------------|---------|
| key       |         | One of `forward`, `backward`, `left`, `right`, `jump`, `sneak`, `sprint` | (empty) |


## Examples
```yaml
Skills:
- message{m="sneaking"} ?ispressingkey{key=sneak} @trigger
```


## Aliases
None.
