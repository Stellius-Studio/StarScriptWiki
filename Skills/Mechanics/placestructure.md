## Description
Places a previously-saved structure template at the target location. No WorldEdit/FAWE
dependency, unlike MythicMobs' own `WEPasteSchematic`.


## Attributes
| Attribute       | Aliases | Description                                                              | Default |
|-----------------|---------|--------------------------------------------------------------------------------|---------|
| id              |         | The structure's namespaced key to place                                          | none (required) |
| rotation        |         | `none`, `cw90`, `cw180`, or `ccw90`                                              | none    |
| mirror          |         | `none`, `frontback`, or `leftright`                                             | none    |
| integrity       |         | `0.0`-`1.0` — chance for each block to actually be placed                       | 1.0     |
| includeentities |         | Whether to place entities that were captured with the structure                  | true    |
| palette         |         | Palette index to use, or `-1` for a random palette                              | -1      |


## Examples
```yaml
Skills:
- placestructure{id=myplugin:arena1} @Ring{radius=0}
```


## Aliases
None.
