## Description
Fires when a world's weather changes (`WeatherChangeEvent`). This is a WORLD-level event with no
real player caster — it uses a virtual caster anchored at the world's spawn location, so
`<trigger.name>` and other player-specific placeholders won't have a real player behind them
here.


## Config
| Attribute | Description                                                                     | Default |
|-----------|----------------------------------------------------------------------------------------|---------|
| to        | Only fire when transitioning TO storming (`true`) or TO clear (`false`); unset fires on both | any     |


## Skill Variables
| Variable        | Description                          |
|-------------------|--------------------------------------------|
| `event-world`      | The world's name                            |
| `event-state`      | The new weather state (boolean, true if now storming) |


## Examples
```yaml
Skills:
- broadcast{m="<gray>Storm clouds gather over <skill.var.event-world>..."} @onlineplayers ~onWeatherChange{to=true}
```


## See Also
- [worldLoad](Skills-Triggers-worldLoad) — another world-level trigger with no real player caster.
