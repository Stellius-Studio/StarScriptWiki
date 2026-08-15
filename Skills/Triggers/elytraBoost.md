## Description
Fires when a player boosts with an elytra and firework (`PlayerElytraBoostEvent`).

`consume=` overrides whether the firework is consumed by this boost — there is no standalone
Bukkit API for this outside the event itself, so the override happens directly in this trigger's
extractor before skill lines fire.


## Config
| Attribute | Description                                           | Default |
|-----------|--------------------------------------------------------|---------|
| consume   | Overrides whether the firework is consumed (`true`/`false`) | vanilla behavior |


## Skill Variables
| Variable        | Description                              |
|-------------------|---------------------------------------------|
| `event-item`        | The material name of the firework used         |
| `event-consume`     | Whether the firework will be consumed (after any `consume=` override) |


## Examples
```yaml
Skills:
- message{m="<aqua>Boosted, firework NOT consumed!"} @trigger ~onElytraBoost{consume=false}
```


## See Also
- [willconsumefirework](Skills-Conditions-willconsumefirework) — condition wrapping `event-consume`.
