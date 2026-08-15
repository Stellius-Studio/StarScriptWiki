## Description
Fires when a player launches a projectile (`ProjectileLaunchEvent`). The target is the projectile
entity.


## Config
| Attribute  | Description                                                       | Default |
|------------|-----------------------------------------------------------------------|---------|
| projectile | Only fire if the projectile type matches (comma-separated list allowed, e.g. `ARROW,TRIDENT`) | any     |


## Skill Variables
| Variable         | Description                    |
|-------------------|------------------------------------|
| `event-projectile`  | The projectile's entity type name     |


## Examples
```yaml
Skills:
- message{m="<aqua>Arrow launched!"} @trigger ~onShoot{projectile=ARROW}
```


## See Also
- [shootBow](Skills-Triggers-shootBow) — fires specifically for bow/crossbow shots, with draw force.
- [projectileHit](Skills-Triggers-projectileHit) — fires when the projectile lands.
