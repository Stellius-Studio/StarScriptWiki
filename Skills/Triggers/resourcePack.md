## Description
Fires when a player responds to a server resource pack prompt (`PlayerResourcePackStatusEvent`).


## Config
| Attribute | Description                                                       | Default |
|-----------|-----------------------------------------------------------------------|---------|
| status    | Only fire if the status matches (e.g. `ACCEPTED`, `DECLINED`, `SUCCESSFULLY_LOADED`, `FAILED_DOWNLOAD`) | any     |


## Skill Variables
| Variable      | Description                    |
|-----------------|--------------------------------------|
| `event-status`    | The resource pack response status name |


## Examples
```yaml
Skills:
- message{m="<red>You declined the resource pack."} @trigger ~onResourcePack{status=DECLINED}
```
