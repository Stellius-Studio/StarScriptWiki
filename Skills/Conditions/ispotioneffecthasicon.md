## Description
True if the caster's active potion effect of the given type has an icon shown in their HUD.


## Attributes
| Attribute | Aliases | Description                                          | Default |
|-----------|---------|-------------------------------------------------------|---------|
| type      |         | The potion effect type to check (e.g. `SPEED`)          | none (required) |


## Examples
```yaml
Skills:
- message{m="has icon"} ?ispotioneffecthasicon{type=SPEED} @trigger
```


## Aliases
None.


## See Also
- [ispotioneffecthasparticles](Skills-Conditions-ispotioneffecthasparticles) — the particles equivalent.
- [ispotiontypeinstant](Skills-Conditions-ispotiontypeinstant) — checks the type itself, not an active effect.
