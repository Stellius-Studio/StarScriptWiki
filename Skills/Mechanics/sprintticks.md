## Description
Requests the server to sprint (run ticks faster than normal) for a number of ticks, or stops
an in-progress sprint.


## Attributes
| Attribute | Aliases | Description                                                     | Default |
|-----------|---------|---------------------------------------------------------------------|---------|
| ticks     |         | Number of ticks to sprint; omit (or `0`) to stop sprinting instead    | 0       |


## Examples
```yaml
Skills:
- sprintticks{ticks=100}
```

```yaml
Skills:
- sprintticks
```


## Aliases
None.
