## Description
Fires when a player's projectile hits something (`ProjectileHitEvent`). The target is the hit
entity (if any) or the hit block's location (if any).


## Config
| Attribute  | Description                                                       | Default |
|------------|-----------------------------------------------------------------------|---------|
| projectile | Only fire if the projectile type matches (comma-separated list allowed) | any     |


## Skill Variables
| Variable         | Description                    |
|-------------------|------------------------------------|
| `event-projectile`  | The projectile's entity type name     |


## Examples
```yaml
Skills:
- message{m="<aqua>Hit!"} @trigger ~onProjectileHit
```


## See Also
- [shoot](Skills-Triggers-shoot) — fires when the projectile is launched.
