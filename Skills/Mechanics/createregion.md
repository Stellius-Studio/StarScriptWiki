## Description
Registers a new persisted named cuboid region between two corners (or replaces the corners
of one with a matching id, indexed for `inregion`/`~onRegionEnter`/`~onRegionExit` lookups).
The world used is the caster's/target's own world. Regions are saved to `regions.yml` and
survive restarts.


## Attributes
| Attribute | Aliases | Description                                | Default |
|-----------|---------|--------------------------------------------------|---------|
| id        |         | The region's id                                     | none (required) |
| corner1   |         | First corner, as an `x,y,z` string                  | none (required) |
| corner2   |         | Second corner, as an `x,y,z` string                 | none (required) |


## Examples
```yaml
Skills:
- createregion{id=spawn_area;corner1="100,60,100";corner2="150,90,150"} @trigger
```


## Aliases
None.
