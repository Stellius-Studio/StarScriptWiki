## Description
Fires when a player dies (`PlayerDeathEvent`). For the "you personally killed someone" trigger,
see [kill](Skills-Triggers-kill) (player victim) or [entityKill](Skills-Triggers-entityKill)
(mob victim) instead — this is the "you personally died" trigger.

Normally StarScript skips execution if the caster is dead, but `~onDeath` is a deliberate
exception: it always runs its skills even though the caster died in the same event.


## Config
| Attribute     | Description                                                     | Default |
|---------------|-----------------------------------------------------------------------|---------|
| cancelmessage | If true, suppresses the death message in chat entirely                   | false   |


## Skill Variables
| Variable        | Description         |
|-------------------|--------------------------|
| `event-message`    | The death message text    |


## Examples
```yaml
Skills:
- message{m="<red>You died! Respawning..."} @trigger ~onDeath{cancelmessage=true}
```

Target is the killer entity, if any — it is not set when there was no killer (e.g. death by fall
damage).


## See Also
- [kill](Skills-Triggers-kill) — fires on the killer when you kill another player.
- [entityKill](Skills-Triggers-entityKill) — fires on the killer when you kill a mob.
