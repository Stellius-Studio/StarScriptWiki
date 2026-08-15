## Description
Toggles MythicEnchants' own debug logging at runtime. Not persisted to `config.yml` — resets to
the configured value on next reload/restart.


## Attributes
| Attribute | Aliases | Description                                       | Default |
|-----------|---------|-------------------------------------------------------|---------|
| state     |         | Whether debug logging should be enabled                | true |


## Examples
```yaml
Skills:
- setmenchdebug{state=true} @trigger
```

```yaml
Skills:
- setmenchdebug{state=false} @trigger
```


## Aliases
None.
