## Description
Fires when a chunk unloads (`ChunkUnloadEvent`). The target location is the chunk's approximate
center.


## Config
| Attribute | Description                       | Default |
|-----------|---------------------------------------|---------|
| world     | Only fire if the world name matches      | any     |


## Skill Variables
| Variable      | Description         |
|-----------------|-------------------------|
| `event-world`     | The chunk's world name    |


## Examples
```yaml
Skills:
- log{m="Chunk unloaded in <skill.var.event-world>"} @trigger ~onChunkUnload
```


## See Also
- [chunkLoad](Skills-Triggers-chunkLoad) — the counterpart trigger.
