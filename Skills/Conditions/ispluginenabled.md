## Description
True if the given plugin is currently enabled.


## Attributes
| Attribute | Aliases | Description                       | Default |
|-----------|---------|----------------------------------------|---------|
| plugin    |         | The plugin's name (case-sensitive, as it appears in `plugins/`) | (empty) |


## Examples
```yaml
Skills:
- message{m="worldguard is enabled"} ?ispluginenabled{plugin=WorldGuard} @trigger
```


## Aliases
None.
