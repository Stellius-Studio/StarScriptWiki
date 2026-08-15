## Description
Fires on the killer when a player kills another player (`PlayerDeathEvent`, killer must be a
player). For a player killing a non-player entity/mob, see
[entityKill](Skills-Triggers-entityKill) instead.


## Config
None.


## Skill Variables
| Variable       | Description         |
|-----------------|--------------------------|
| `event-victim`   | The victim player's name  |


## Examples
```yaml
Skills:
- message{m="<red><trigger.name> defeated <skill.var.event-victim>!"} @onlineplayers ~onKill
```


## See Also
- [entityKill](Skills-Triggers-entityKill) — the mob-victim equivalent, with `entity=`/`mythicmob=` filters.
