## Description
Replaces an existing region's cuboid bounds with a new pair of corners (same world as the
region already uses).


## Attributes
| Attribute | Aliases | Description                          | Default |
|-----------|---------|--------------------------------------------|---------|
| id        |         | The region's id                              | none (required) |
| corner1   |         | New first corner, as an `x,y,z` string       | none (required) |
| corner2   |         | New second corner, as an `x,y,z` string      | none (required) |


## Examples
```yaml
Skills:
- resizeregion{id=spawn_area;corner1="90,60,90";corner2="160,95,160"}
```


## Aliases
None.
