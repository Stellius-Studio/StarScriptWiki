## Description
Fires when an entity receives knockback (`EntityKnockbackEvent`). The caster and target are
the entity being knocked back. If the knockback came from another entity's attack (`
EntityPushedByEntityAttackEvent`), the trigger entity is set to the attacker and
`event-attacker` is populated.


## Config
| Attribute | Description                                      | Default |
|-----------|-----------------------------------------------------|---------|
| entity    | Only fire if the knocked-back entity's type matches   | any     |


## Skill Variables
| Variable         | Description                                                      |
|------------------|----------------------------------------------------------------------|
| `event-cause`      | The `EntityKnockbackEvent.Cause` name                               |
| `event-attacker`   | The attacker's entity type name (only set for attack-caused knockback) |


## Examples
```yaml
Skills:
- message{m="<red>Knocked back!"} @trigger ~onEntityKnockback{entity=PLAYER}
```
