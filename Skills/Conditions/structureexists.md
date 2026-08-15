## Description
True if a structure template with the given id has been saved.


## Attributes
| Attribute | Aliases | Description             | Default |
|-----------|---------|-------------------------------|---------|
| id        |         | The structure's namespaced key   | none (required) |


## Examples
```yaml
Skills:
- placestructure{id=myplugin:arena1} ?structureexists{id=myplugin:arena1} @Ring{radius=0}
```


## Aliases
None.
