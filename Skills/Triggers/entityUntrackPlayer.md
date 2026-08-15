## Description
Fires when a player stops tracking (no longer renders/receives packets for) an entity
(`io.papermc.paper.event.player.PlayerUntrackEntityEvent`).


## Config
| Attribute | Description                                 | Default |
|-----------|--------------------------------------------------|---------|
| entity    | Only fire if the untracked entity's type matches    | any     |


## Skill Variables
| Variable       | Description                     |
|----------------|------------------------------------|
| `event-entity`   | The untracked entity's type name   |


## Examples
```yaml
Skills:
- message{m="<gray>A nearby <skill.var.event-entity> left your view."} @trigger ~onEntityUntrackPlayer
```
