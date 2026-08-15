## Description
Fires when a player starts tracking (rendering/receiving packets for) an entity
(`io.papermc.paper.event.player.PlayerTrackEntityEvent`).


## Config
| Attribute | Description                                 | Default |
|-----------|--------------------------------------------------|---------|
| entity    | Only fire if the tracked entity's type matches      | any     |


## Skill Variables
| Variable       | Description                    |
|----------------|-----------------------------------|
| `event-entity`   | The tracked entity's type name    |


## Examples
```yaml
Skills:
- message{m="<gray>You can now see a nearby <skill.var.event-entity>."} @trigger ~onEntityTrackPlayer
```
