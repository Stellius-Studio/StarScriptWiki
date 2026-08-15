## Description
Fires when a player harvests a block (e.g. a fully-grown crop) with the harvest tool interaction
(`PlayerHarvestBlockEvent`). The target location is the harvested block.


## Config
| Attribute | Description                                     | Default |
|-----------|-----------------------------------------------------|---------|
| block     | Only fire if the harvested block matches this material name | any     |


## Skill Variables
| Variable      | Description                        |
|-----------------|-----------------------------------------|
| `event-block`     | The material name of the harvested block  |


## Examples
```yaml
Skills:
- message{m="<green>Harvested!"} @trigger ~onHarvestBlock{block=WHEAT}
```
