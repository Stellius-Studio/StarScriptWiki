## Description
True if the caster's item matches a single prefixed custom-item ref, e.g. `nexo:foo`,
`mythic:bar`, `itemsadder:ns:id`, `craftengine:ns:id`.


## Attributes
| Attribute | Aliases | Description                                                                | Default |
|-----------|---------|------------------------------------------------------------------------------|---------|
| ref       |         | The prefixed custom-item ref to match                                        | none (required) |
| slot      |         | Which equipment slot's item to check — `hand`, `offhand`, `head`, `chest`, `legs`, `feet` | hand |


## Examples
```yaml
Skills:
- message{m="You're holding the Cursebreaker Blade!"} ?matchesmenchitemref{ref=mythic:cursebreaker_blade} @trigger
```


## Aliases
None.
