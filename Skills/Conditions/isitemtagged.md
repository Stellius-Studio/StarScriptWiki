## Description
True if the caster's main-hand item is tagged with the given vanilla item tag (e.g. `logs`,
`planks`, `wool`).


## Attributes
| Attribute | Aliases | Description                                                    | Default |
|-----------|---------|----------------------------------------------------------------|---------|
| tag       |         | The vanilla item tag name (without the `minecraft:` prefix), e.g. `logs` | none (required) |


## Examples
```yaml
Skills:
- message{m="is a log"} ?isitemtagged{tag=logs} @trigger
```


## Aliases
None.
