## Description
True if a persisted region with the given id is registered.


## Attributes
| Attribute | Aliases | Description       | Default |
|-----------|---------|-------------------------|---------|
| id        |         | The region's id            | none (required) |


## Examples
```yaml
Skills:
- message{m="Region exists."} ?regionexists{id=spawn_area} @trigger
```


## Aliases
None.
