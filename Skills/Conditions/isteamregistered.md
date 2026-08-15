## Description
True if a scoreboard team with the given id exists on the main scoreboard.


## Attributes
| Attribute | Aliases | Description       | Default |
|-----------|---------|-------------------------|---------|
| team      |         | The team id to check       | none (required) |


## Examples
```yaml
Skills:
- message{m="Red Team exists"} ?isteamregistered{team=red_team} @trigger
```


## Aliases
None.
