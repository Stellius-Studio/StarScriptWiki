## Description
Fires when a portal is created (`PortalCreateEvent`).


## Config
| Attribute | Description                                                    | Default |
|-----------|-----------------------------------------------------------------|---------|
| reason    | Only fire if the creation reason matches (e.g. `FIRE`, `NETHER_PAIR`, `END_PLATFORM`) | any     |


## Skill Variables
| Variable      | Description               |
|-----------------|--------------------------------|
| `event-reason`    | The portal creation reason name |


## Examples
```yaml
Skills:
- message{m="<purple>Portal created!"} @trigger ~onPortalCreate
```
