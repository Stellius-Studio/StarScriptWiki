## Description
Fires when a world finishes loading (`WorldLoadEvent`). This is a WORLD-level event with no real
player caster — it uses a virtual caster anchored at the world's spawn location, so
`<trigger.name>` and other player-specific placeholders won't have a real player behind them
here.


## Config
| Attribute | Description                | Default |
|-----------|----------------------------------|---------|
| world     | Only fire for this world name         | any     |


## Skill Variables
| Variable        | Description        |
|-------------------|--------------------------|
| `event-world`      | The world's name          |


## Examples
```yaml
Skills:
- log{m="World <skill.var.event-world> finished loading."} @onlineplayers ~onWorldLoad
```


## See Also
- [weatherChange](Skills-Triggers-weatherChange) — another world-level trigger with no real player caster.
