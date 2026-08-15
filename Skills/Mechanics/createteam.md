## Description
Registers a new scoreboard team, or reconfigures it if the id already exists. Every field
except `id=` is optional — only fields you provide are changed.


## Attributes
| Attribute               | Aliases | Description                                                                 | Default |
|--------------------------|---------|---------------------------------------------------------------------------------|---------|
| id                       |         | The team's id                                                                     | none (required) |
| displayname              |         | The team's display name (MiniMessage)                                            | unchanged |
| color                    |         | The team's color, a `ChatColor` name (e.g. `RED`, `AQUA`)                        | unchanged |
| collisionrule            |         | `always`/`never`/`forownteam`/`forotherteams`                                    | unchanged |
| deathmessagevisibility   |         | `always`/`never`/`forownteam`/`forotherteams`                                    | unchanged |
| nametagvisibility        |         | `always`/`never`/`forownteam`/`forotherteams`                                    | unchanged |
| friendlyfire             |         | Whether team members can damage each other                                       | unchanged |
| seefriendlyinvisibles    |         | Whether team members can see each other while invisible                          | unchanged |
| prefix                   |         | The team's nametag prefix (MiniMessage)                                          | unchanged |
| suffix                   |         | The team's nametag suffix (MiniMessage)                                          | unchanged |


## Examples
```yaml
Skills:
- createteam{id=red_team;displayname="<red>Red Team";color=RED;friendlyfire=false}
```


## Aliases
None.
