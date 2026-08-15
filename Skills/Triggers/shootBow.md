## Description
Fires when a player shoots a bow or crossbow (`EntityShootBowEvent`).


## Config
| Attribute | Description                                       | Default |
|-----------|-----------------------------------------------------|---------|
| item      | Only fire if the bow/crossbow used matches this material name | any     |


## Skill Variables
| Variable      | Description                        |
|-----------------|-----------------------------------------|
| `event-force`     | The draw force the bow was released at (0.0-1.0) |


## Examples
```yaml
Skills:
- message{m="<aqua>Full draw!"} @trigger ~onShootBow
```


## See Also
- [shoot](Skills-Triggers-shoot) — the more general projectile-launch trigger.
