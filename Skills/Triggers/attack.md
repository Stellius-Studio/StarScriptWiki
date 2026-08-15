## Description
Fires on the attacking player when they damage another entity (`EntityDamageByEntityEvent`,
resolved to the attacking player). This works even if the player attacked indirectly via a shot
projectile such as an arrow. This fires on the ATTACKER — contrast with
[damageByEntity](Skills-Triggers-damageByEntity), which fires on the victim. The target is the
entity that got hit.

If MythicCrucible is installed, note it registers its own damage triggers at a higher event
priority and can cancel this event first — see [Universal trigger token
options](Skills-Scripts#universal-trigger-token-options) if this trigger needs to run
regardless of what else is listening.


## Config
| Attribute | Description                             | Default |
|-----------|----------------------------------------------|---------|
| entity    | Entity type filter on the entity being hit         | any     |


## Skill Variables
| Variable        | Description             |
|-------------------|------------------------------|
| `event-damage`     | The damage amount (double)    |


## Examples
```yaml
Skills:
- message{m="<green>You hit a <target.type> for <skill.var.event-damage>!"} @trigger ~onAttack{entity=ZOMBIE}
```


## See Also
- [damageByEntity](Skills-Triggers-damageByEntity) — the victim's-perspective equivalent.
