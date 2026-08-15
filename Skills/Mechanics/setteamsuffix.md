## Description
Sets a scoreboard team's nametag suffix. Registered together with `setteamprefix` (same
mechanic class, dispatched by which name it's invoked under) — see
[setteamprefix](Skills-Mechanics-setteamprefix) for the prefix equivalent and full field
reference.


## Attributes
| Attribute | Aliases | Description                    | Default |
|-----------|---------|-------------------------------------|---------|
| team      |         | The team's id                         | none (required) |
| value     |         | The suffix text (MiniMessage)         | none (required) |


## Examples
```yaml
Skills:
- setteamsuffix{team=red_team;value=" <gray>[VIP]"}
```


## Aliases
None.
