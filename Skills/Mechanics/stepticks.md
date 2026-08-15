## Description
Steps the game forward a number of ticks while the server is frozen (see `setfrozen`), or
stops an in-progress step.


## Attributes
| Attribute | Aliases | Description                                                   | Default |
|-----------|---------|-------------------------------------------------------------------|---------|
| ticks     |         | Number of ticks to step; omit (or `0`) to stop stepping instead     | 0       |


## Examples
```yaml
Skills:
- setfrozen
- stepticks{ticks=1}
```


## Aliases
None.
