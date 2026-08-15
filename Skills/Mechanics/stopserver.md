## Description
Shuts down the server, optionally broadcasting a message first.

This is irreversible and affects the whole server — it also always logs a warning to the console
on invocation so an accidental trigger is never silent.


## Attributes
| Attribute | Aliases | Description                                    | Default |
|-----------|---------|-----------------------------------------------------|---------|
| message   | m       | A message to broadcast to all players before shutdown | none    |


## Examples
```yaml
ScheduledRestart:
  Skills:
  - stopserver{message="<red>Server restarting for maintenance!"} @trigger
```


## Aliases
None.
