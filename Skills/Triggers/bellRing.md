## Description
Fires when a bell is rung (`BellRingEvent`). Fires with a player context if a player rang it,
otherwise a location-only context. The target location is the bell.


## Config
None.


## Skill Variables
None.


## Examples
```yaml
Skills:
- message{m="<yellow>Bell rung!"} @trigger ~onBellRing
```


## See Also
- [isbellringing](Skills-Conditions-isbellringing) / [isbellresonating](Skills-Conditions-isbellresonating) — bell state conditions.
