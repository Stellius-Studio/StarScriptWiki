## Description
Fires when a player kills a non-player entity (`EntityDeathEvent`, killer must be a player). For
a player killing another player, see [kill](Skills-Triggers-kill) instead.


## Config
| Attribute | Description                                                                 | Default |
|-----------|----------------------------------------------------------------------------|---------|
| entity    | Only fire if the victim's Bukkit entity type matches (e.g. `ZOMBIE`)       | any     |
| mythicmob | Only fire if the victim was a MythicMobs mob with this internal type name | any     |


## Skill Variables
| Variable            | Description                                                          |
|----------------------|------------------------------------------------------------------------|
| `event-entity`         | The victim's Bukkit entity type name                                    |
| `event-mythic-type`    | The victim's MythicMobs internal type name, or empty if it wasn't a MythicMobs mob |


## Examples
```yaml
Skills:
- message{m="<green>Zombie down!"} @trigger ~onEntityKill{entity=ZOMBIE}
```

```yaml
# Only fires for a specific MythicMobs mob type, regardless of its underlying vanilla entity type.
Skills:
- message{m="<gold>You slew the Zombie Boss!"} @trigger ~onEntityKill{mythicmob=ZombieBoss}
```

`entity=` and `mythicmob=` can be combined — both must match if both are set.


## See Also
- [kill](Skills-Triggers-kill) — the player-victim equivalent.
