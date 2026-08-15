## Description
Fires when a chunk loads (`ChunkLoadEvent`). The target location is the chunk's approximate
center.


## Config
| Attribute | Description                                       | Default |
|-----------|-----------------------------------------------------|---------|
| world     | Only fire if the world name matches                    | any     |
| newonly   | If `true`, only fire for newly-generated chunks (not previously-saved ones) | false   |


## Skill Variables
| Variable      | Description         |
|-----------------|-------------------------|
| `event-world`     | The chunk's world name    |


## Examples
```yaml
Skills:
- log{m="Chunk loaded in <skill.var.event-world>"} @trigger ~onChunkLoad
```


## See Also
- [chunkUnload](Skills-Triggers-chunkUnload) — the counterpart trigger.
- [ischunkloaded](Skills-Conditions-ischunkloaded) — condition to check chunk-loaded state directly.
