## Description
True if the caster's/target's player is an owner of the given region.


## Attributes
| Attribute | Aliases | Description       | Default |
|-----------|---------|-------------------------|---------|
| id        |         | The region's id            | none (required) |


## Examples
```yaml
Skills:
- deleteregion{id=my_house} ?isregionowner{id=my_house} @trigger
```


## Aliases
None.
