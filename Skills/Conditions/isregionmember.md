## Description
True if the caster's/target's player is a member (or owner) of the given region.


## Attributes
| Attribute | Aliases | Description       | Default |
|-----------|---------|-------------------------|---------|
| id        |         | The region's id            | none (required) |


## Examples
```yaml
Skills:
- message{m="Welcome home!"} ?isregionmember{id=my_house} @trigger
```


## Aliases
None.
