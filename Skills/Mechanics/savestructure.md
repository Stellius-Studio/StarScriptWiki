## Description
Captures the block region between two corners into a named structure template, saved via
Bukkit's `StructureManager` — no WorldEdit/FAWE dependency, unlike MythicMobs' own
`WEPasteSchematic`. The world used is the caster's/target's own world.


## Attributes
| Attribute       | Aliases | Description                                                       | Default |
|-----------------|---------|-------------------------------------------------------------------------|---------|
| id              |         | The structure's namespaced key to save under                             | none (required) |
| corner1         |         | First corner, as an `x,y,z` string                                       | none (required) |
| corner2         |         | Second corner, as an `x,y,z` string                                      | none (required) |
| includeentities |         | Whether to capture entities standing in the region                        | true    |


## Examples
```yaml
Skills:
- savestructure{id=myplugin:arena1;corner1=100,64,100;corner2=120,80,120} @trigger
```


## Aliases
None.
