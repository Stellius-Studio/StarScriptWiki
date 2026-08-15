## Description
Fires when a player teleports (`PlayerTeleportEvent`). Origin is set to the FROM location, and
target is set to the TO location (both only if non-null).


## Config
| Attribute | Description                                                              | Default |
|-----------|---------------------------------------------------------------------------------|---------|
| cause     | Only fire if the teleport cause matches (matches `TeleportCause`, e.g. `COMMAND`, `PLUGIN`, `ENDER_PEARL`, `CHORUS_FRUIT`) | any     |


## Skill Variables
| Variable       | Description        |
|------------------|--------------------------|
| `event-cause`     | The teleport cause name   |


## Examples
```yaml
Skills:
- particle{p=portal} @origin ~onTeleport{cause=ENDER_PEARL}
```


## See Also
- [portal](Skills-Triggers-portal) — the portal-specific equivalent.
