## Description
True if the elytra boost will consume its firework. Only meaningful inside a skill bound to the
[elytraBoost](Skills-Triggers-elytraBoost) trigger — it reads the `event-consume` skill variable that trigger exposes.


## Attributes
None.


## Examples
```yaml
Skills:
- message{m="firework will be consumed"} ?willconsumefirework @trigger ~onElytraBoost
```


## Aliases
None.


## See Also
- [elytraBoost](Skills-Triggers-elytraBoost) — the trigger this reads from. Supports `consume=` config to override whether
  the firework is consumed.
