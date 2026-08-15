## Description
Adds or removes the caster (or target entity) from a team by its scoreboard "entry"
(name/UUID string). Targets the caster if it's not a targeted-entity mechanic, otherwise the
skill's entity target.


## Attributes
| Attribute | Aliases | Description                          | Default |
|-----------|---------|-------------------------------------------|---------|
| team      |         | The team's id                               | none (required) |
| remove    |         | `true` removes the entry instead of adding it | false |


## Examples
```yaml
Skills:
- teamentry{team=red_team} @trigger
```

```yaml
Skills:
- teamentry{team=red_team;remove=true} @trigger
```


## Aliases
None.
