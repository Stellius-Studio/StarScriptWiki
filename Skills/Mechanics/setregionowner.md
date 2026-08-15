## Description
Adds or removes the caster's/target's player as an owner of a region. Owners are also
implicitly members (see `isregionmember`).


## Attributes
| Attribute | Aliases | Description                        | Default |
|-----------|---------|------------------------------------------|---------|
| id        |         | The region's id                            | none (required) |
| remove    |         | `true` removes the player as owner instead of adding | false |


## Examples
```yaml
Skills:
- setregionowner{id=my_house} @trigger
```

```yaml
Skills:
- setregionowner{id=my_house;remove=true} @trigger
```


## Aliases
None.
