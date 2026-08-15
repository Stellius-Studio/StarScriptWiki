## Description
Removes the caster's/target's player from a region's member list. Does not affect ownership
— use `setregionowner{remove=true}` to remove an owner.


## Attributes
| Attribute | Aliases | Description       | Default |
|-----------|---------|-------------------------|---------|
| id        |         | The region's id            | none (required) |


## Examples
```yaml
Skills:
- removeregionmember{id=my_house} @trigger
```


## Aliases
None.
