## Description
Fires when a player takes damage from another entity (`EntityDamageByEntityEvent`, player victims
only). This fires on the VICTIM — the player who got hit. For the attacker's perspective, see
[attack](Skills-Triggers-attack) instead. The target is the damager entity.

If MythicCrucible is installed, note it registers its own damage triggers at a higher event
priority and can cancel this event first — see [Universal trigger token
options](Skills-Scripts#universal-trigger-token-options) if this trigger needs to run
regardless of what else is listening.


## Config
| Attribute | Description                              | Default |
|-----------|-----------------------------------------------|---------|
| entity    | Entity type filter on the damager                  | any     |


## Skill Variables
| Variable        | Description                    |
|-------------------|--------------------------------------|
| `event-damage`     | The damage amount (double)            |
| `event-entity`     | The damager's entity type name        |


## Examples
```yaml
Skills:
- message{m="<red>Hit by a <skill.var.event-entity> for <skill.var.event-damage>!"} @trigger ~onDamageByEntity{entity=ZOMBIE}
```


## See Also
- [attack](Skills-Triggers-attack) — the attacker's-perspective equivalent.
- [damage](Skills-Triggers-damage) — fires for any damage cause, not just entity damagers.
