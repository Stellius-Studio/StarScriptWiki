## Description
True if the caster/target is currently inside the given (or, if `id=` is omitted, any)
persisted region.


## Attributes
| Attribute | Aliases | Description                                        | Default |
|-----------|---------|-----------------------------------------------------------|---------|
| id        |         | The region's id to check; omit to check "inside any region" | any region |


## Examples
```yaml
Skills:
- message{m="You're in the spawn area!"} ?inregion{id=spawn_area} @trigger
```

```yaml
Skills:
- message{m="You're inside a claimed region."} ?inregion @trigger
```


## Aliases
None.
