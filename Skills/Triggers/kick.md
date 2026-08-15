## Description
Fires when a player is kicked (`PlayerKickEvent`).


## Config
None.


## Skill Variables
| Variable        | Description         |
|-------------------|------------------------|
| `event-reason`     | The kick reason text     |


## Examples
```yaml
Skills:
- log{m="<skill.caster.name> was kicked: <skill.var.event-reason>"} @trigger ~onKick
```
