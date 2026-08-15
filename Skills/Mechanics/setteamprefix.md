## Description
Sets a scoreboard team's nametag prefix. Registered together with `setteamsuffix` (same
mechanic class, dispatched by which name it's invoked under) — see
[setteamsuffix](Skills-Mechanics-setteamsuffix) for the suffix equivalent.


## Attributes
| Attribute | Aliases | Description                    | Default |
|-----------|---------|-------------------------------------|---------|
| team      |         | The team's id                         | none (required) |
| value     |         | The prefix text (MiniMessage)         | none (required) |


## Examples
```yaml
Skills:
- setteamprefix{team=red_team;value="<red>[Red] "}
```


## Aliases
None.
