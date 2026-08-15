## Description
Writes a typed value to the MongoDB-backed variable store, scoped globally (shared server-wide,
the default), per-player, or per-skill-caster (any entity, not just players).

Requires `Storage.Mongo.Enabled: true` in config.yml (disabled by default — needs a running
`mongod`). If Mongo isn't enabled or failed to connect, this returns `INVALID_CONFIG`.

Writes are cached in memory immediately and persisted asynchronously, so this never blocks the
calling skill.


## Attributes
| Attribute | Aliases | Description                                                       | Default |
|-----------|---------|-------------------------------------------------------------------------|---------|
| var       |         | The variable name                                                        | none (required) |
| val       | value   | The value to store                                                       | (empty) |
| type      |         | `STRING`, `INT`, `FLOAT`, or `BOOL` — governs how `addmongo` parses it later | STRING  |
| scope     |         | `global` (shared server-wide), `player` (per-caster, players only), `skill` (per-caster, any entity), or `custom` (an arbitrary shared group — see `group=` below) | global  |
| group     |         | Group name for `scope=custom` (e.g. a quest party ID) — supports placeholders like `<skill.var.x>`, so every caster that resolves to the SAME group name shares the same value. Required when `scope=custom`. | (none) |


## Examples
```yaml
SetRedScore:
  Skills:
  - setmongo{var=score_red;val=27;type=FLOAT} @trigger
```

```yaml
# Every member of the same quest party shares ONE progress value.
SetPartyQuestProgress:
  Skills:
  - setmongo{var=quest_progress;val=3;type=INT;scope=custom;group=<skill.var.party_id>} @trigger
```


## Aliases
None.


## See Also
- [getmongo](Skills-Mechanics-getmongo) — read a variable into a skill variable.
- [unsetmongo](Skills-Mechanics-unsetmongo) — delete a variable.
- [addmongo](Skills-Mechanics-addmongo) — add to/subtract from a numeric variable.
- [setsql](Skills-Mechanics-setsql) / [setredis](Skills-Mechanics-setredis) — same shape, SQL/Redis-backed.
