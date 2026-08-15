## Description
Fires when a player takes damage from any source (`EntityDamageEvent`, player victims only).

If MythicCrucible is installed, note it registers its own damage triggers at a higher event
priority and can cancel this event first — see [Universal trigger token
options](Skills-Scripts#universal-trigger-token-options) if this trigger needs to run
regardless of what else is listening.


## Config
| Attribute | Description                                                             | Default |
|-----------|--------------------------------------------------------------------------------|---------|
| cause     | Comma-separated list of `EntityDamageEvent.DamageCause` names (e.g. `FALL,FIRE,DROWNING`) | any     |


## Skill Variables
| Variable        | Description                    |
|-------------------|--------------------------------------|
| `event-cause`      | The damage cause name                 |
| `event-damage`     | The damage amount (double)            |


## Examples
```yaml
Skills:
- message{m="<red>Ouch, watch your fall damage!"} @trigger ~onDamage{cause=FALL}
```


## See Also
- [damageByEntity](Skills-Triggers-damageByEntity) — fires specifically when another entity caused the damage, with the damager as target.
- [attack](Skills-Triggers-attack) — fires on the attacker instead of the victim.
