## Description
Deletes a Redis-backed variable.

Requires `Storage.Redis.Enabled: true` in config.yml. If Redis isn't enabled or failed to
connect, this returns `INVALID_CONFIG`.


## Attributes
| Attribute | Aliases | Description                                                | Default |
|-----------|---------|----------------------------------------------------------------|---------|
| var       |         | The variable name to delete                                     | none (required) |
| scope     |         | `global`, `player`, `skill`, or `custom` (an arbitrary shared group — see `group=` below) — must match how it was written | global  |
| group     |         | Group name for `scope=custom` (e.g. a quest party ID) — supports placeholders like `<skill.var.x>`, so every caster that resolves to the SAME group name shares the same value. Required when `scope=custom`. | (none) |


## Examples
```yaml
ClearRedScore:
  Skills:
  - unsetredis{var=score_red} @trigger
```

```yaml
# Delete the quest progress value shared by every member of the same party.
ClearPartyQuestProgress:
  Skills:
  - unsetredis{var=quest_progress;scope=custom;group=<skill.var.party_id>} @trigger
```


## Aliases
None.


## See Also
- [setredis](Skills-Mechanics-setredis) — write a value.
- [unsetsql](Skills-Mechanics-unsetsql) / [unsetmongo](Skills-Mechanics-unsetmongo) — same shape, SQL/MongoDB-backed.
