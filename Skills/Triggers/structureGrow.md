## Description
Fires when a structure grows (e.g. a tree from a sapling, or a giant mushroom)
(`StructureGrowEvent`). Fires with a player context if a player caused it (e.g. via bonemeal),
otherwise a location-only context. The target location is the structure's origin.


## Config
None.


## Skill Variables
| Variable       | Description                     |
|------------------|--------------------------------------|
| `event-species`    | The tree/structure species name          |


## Examples
```yaml
Skills:
- message{m="<green>A tree grew!"} @trigger ~onStructureGrow
```
