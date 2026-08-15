## Description
Fires when a world is unloaded (`WorldUnloadEvent`).


## Config
| Attribute | Description                       | Default |
|-----------|---------------------------------------|---------|
| world     | Only fire if the world name matches      | any     |


## Skill Variables
| Variable      | Description         |
|-----------------|-------------------------|
| `event-world`     | The unloaded world's name |


## Examples
```yaml
Skills:
- log{m="World <skill.var.event-world> unloaded."} @trigger ~onWorldUnload
```


## See Also
- [worldsave](Skills-Mechanics-worldsave) — the mechanic supports `unload=true` to trigger this directly.
