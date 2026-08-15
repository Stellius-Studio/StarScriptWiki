## Description
Fires when a MythicEnchants enchantment's own internal trigger system fires a named trigger
(`MenchTriggerFireEvent`) — the mechanism MythicEnchants uses to fan out enchant-driven combat/use
events by name.

**Important caveat:** `MenchTriggerFireEvent` only fires for trigger names something has actively
subscribed to via `MythicEnchantsAPI#subscribeToTrigger`. StarScript automatically subscribes to
every distinct `trigger=` value used across all `~onMenchTriggerFire{trigger=...}` bindings in
loaded scripts, resubscribing/unsubscribing as scripts are (re)loaded. **A binding with no
`trigger=` filter (i.e. wanting to catch every trigger name) is never subscribed to anything and
will simply never fire** — always set `trigger=` to the specific name you want to react to.


## Config
| Attribute | Description                                       | Default |
|-----------|------------------------------------------------------|---------|
| trigger   | Only fire if the trigger name matches this (required in practice — see caveat above) | any (but never fires unsubscribed) |


## Skill Variables
| Variable            | Description                                       |
|---------------------|--------------------------------------------------------|
| `event-trigger-name`  | The fired trigger's name                                |
| `event-damage`        | The damage amount associated with the trigger, if any   |


## Examples
```yaml
Skills:
- message{m="<red>Your weapon's ON_HIT trigger fired!"} @trigger ~onMenchTriggerFire{trigger=ON_HIT}
```

```yaml
Skills:
- damage{amount=5} @target ~onMenchTriggerFire{trigger=ON_CRIT}
```
