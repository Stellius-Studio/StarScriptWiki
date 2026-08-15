## Description
Fires when a player enters a portal (`PlayerPortalEvent`).


## Config
| Attribute | Description                                                     | Default |
|-----------|------------------------------------------------------------------------|---------|
| cause     | Only fire if the teleport cause matches (matches `PlayerTeleportEvent.TeleportCause`, e.g. `NETHER_PORTAL`, `END_PORTAL`) | any     |


## Skill Variables
| Variable       | Description        |
|------------------|--------------------------|
| `event-cause`     | The teleport cause name   |


## Examples
```yaml
Skills:
- message{m="<red>The Nether awaits..."} @trigger ~onPortal{cause=NETHER_PORTAL}
```


## See Also
- [teleport](Skills-Triggers-teleport) — fires for any teleport, with origin/target locations.
