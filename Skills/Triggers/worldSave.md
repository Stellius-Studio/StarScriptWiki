## Description
Fires when a world is saved (`WorldSaveEvent`).


## Config
| Attribute | Description                       | Default |
|-----------|---------------------------------------|---------|
| world     | Only fire if the world name matches      | any     |


## Skill Variables
| Variable      | Description         |
|-----------------|-------------------------|
| `event-world`     | The saved world's name    |


## Examples
```yaml
Skills:
- log{m="World <skill.var.event-world> saved."} @trigger ~onWorldSave
```


## See Also
- [worldsave](Skills-Mechanics-worldsave) — the mechanic to save a world on demand.
