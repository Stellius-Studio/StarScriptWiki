## Description
Fires when a player toggles sneaking (`PlayerToggleSneakEvent`).


## Config
| Attribute | Description                                                                       | Default |
|-----------|------------------------------------------------------------------------------------------|---------|
| state     | Only fire when transitioning to this specific sneaking state (`true`/`false`); unset fires on both sneak start and stop | any     |


## Skill Variables
| Variable       | Description                    |
|------------------|--------------------------------------|
| `event-state`     | The new sneaking state (boolean)      |


## Examples
```yaml
Skills:
- particle{p=smoke} @trigger ~onSneak{state=true}
```


## See Also
- [sprint](Skills-Triggers-sprint) — the sprinting equivalent.
