## Description
Deletes a SQL-backed variable.


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
  - unsetsql{var=score_red} @trigger
```

```yaml
# Delete the quest progress value shared by every member of the same party.
ClearPartyQuestProgress:
  Skills:
  - unsetsql{var=quest_progress;scope=custom;group=<skill.var.party_id>} @trigger
```


## Aliases
None.


## See Also
- [setsql](Skills-Mechanics-setsql) — write a value.
- [unsetmongo](Skills-Mechanics-unsetmongo) / [unsetredis](Skills-Mechanics-unsetredis) — same shape, MongoDB/Redis-backed.
