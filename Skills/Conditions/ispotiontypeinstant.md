## Description
True if the named potion effect type is instant (e.g. `INSTANT_HEALTH`, `INSTANT_DAMAGE`).

This checks a static property of the type itself — no active effect needs to be present on the
caster.


## Attributes
| Attribute | Aliases | Description                                          | Default |
|-----------|---------|-------------------------------------------------------|---------|
| type      |         | The potion effect type to check (e.g. `INSTANT_HEALTH`) | none (required) |


## Examples
```yaml
Skills:
- message{m="is instant"} ?ispotiontypeinstant{type=INSTANT_HEALTH} @trigger
```


## Aliases
None.
