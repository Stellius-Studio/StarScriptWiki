## Description
True if the caster has the given vanilla scoreboard tag (as set via the `/tag` command or
`Entity#addScoreboardTag`). Works on any entity, not just players.


## Attributes
| Attribute | Aliases | Description               | Default |
|-----------|---------|-------------------------------|---------|
| tag       |         | The scoreboard tag to check for | (empty) |


## Examples
```yaml
Skills:
- message{m="has tag"} ?hasscoreboardtag{tag=KilledBoss1} @trigger
```


## Aliases
None.
