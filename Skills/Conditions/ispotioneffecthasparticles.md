## Description
True if the caster's active potion effect of the given type has particles.


## Attributes
| Attribute | Aliases | Description                                          | Default |
|-----------|---------|-------------------------------------------------------|---------|
| type      |         | The potion effect type to check (e.g. `SPEED`)          | none (required) |


## Examples
```yaml
Skills:
- message{m="has particles"} ?ispotioneffecthasparticles{type=SPEED} @trigger
```


## Aliases
None.


## See Also
- [ispotioneffecthasicon](Skills-Conditions-ispotioneffecthasicon) — the icon equivalent.
