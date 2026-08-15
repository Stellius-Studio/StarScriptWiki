## Description
Fires when a player moves (`PlayerMoveEvent`). By default only fires on a full-block change (to
avoid firing every tick of sub-block movement); `fullmove=true` fires on every movement event
instead. The origin is the player's previous location, the target is their new location.


## Config
| Attribute | Description                                                    | Default |
|-----------|--------------------------------------------------------------------|---------|
| fullmove  | If `true`, fires on every movement instead of only full-block changes | false   |


## Skill Variables
None.


## Examples
```yaml
Skills:
- message{m="<aqua>You moved!"} @trigger ~onMove
```
