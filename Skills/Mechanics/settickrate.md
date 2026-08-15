## Description
Sets the server's tick rate (ticks per second). Values outside `1.0`-`10000.0` are rejected by
the server itself (no-op).


## Attributes
| Attribute | Aliases | Description                                        | Default |
|-----------|---------|-------------------------------------------------------|---------|
| rate      |         | Target ticks per second (`1.0`-`10000.0`); vanilla default is `20.0` | 20.0 |


## Examples
```yaml
Skills:
- settickrate{rate=10.0}
```


## Aliases
None.
