## Description
Fires when a player interacts with the world (`PlayerInteractEvent`) — right-clicking or
left-clicking a block or air.

If MythicCrucible is installed, note it registers its own interact trigger at a higher event
priority (`HIGHEST`) — see [Universal trigger token
options](Skills-Scripts#universal-trigger-token-options) if this trigger needs to run before
or regardless of what else is listening.


## Config
| Attribute | Description                                                                          | Default |
|-----------|-------------------------------------------------------------------------------------------|---------|
| action    | Comma-separated list of Bukkit `Action` names to filter on (e.g. `RIGHT_CLICK_BLOCK,LEFT_CLICK_AIR`) | any     |
| block     | Material filter, only checked if a block was clicked                                          | any     |
| hand      | `HAND` or `OFF_HAND`                                                                       | any     |


## Skill Variables
| Variable        | Description                                                                    |
|-------------------|-------------------------------------------------------------------------------------|
| `event-action`     | The `Action` enum name                                                              |
| `event-block`      | Only set if a block was clicked — the block's material name; the target is also set to the clicked block's location in that case |


## Examples
```yaml
Skills:
- message{m="<gray>You right-clicked <skill.var.event-block>."} @trigger ~onInteract{action=RIGHT_CLICK_BLOCK}
```
