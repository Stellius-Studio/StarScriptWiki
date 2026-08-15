## Description
Sets one option (collision rule, death message visibility, or nametag visibility) on a team.


## Attributes
| Attribute | Aliases | Description                                                        | Default |
|-----------|---------|-------------------------------------------------------------------------|---------|
| team      |         | The team's id                                                             | none (required) |
| option    |         | `collisionrule`, `deathmessagevisibility`, or `nametagvisibility`          | none (required) |
| status    |         | `always`, `never`, `forownteam`, or `forotherteams`                       | none (required) |


## Examples
```yaml
Skills:
- setteamoption{team=red_team;option=nametagvisibility;status=never}
```


## Aliases
None.
