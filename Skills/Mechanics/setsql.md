## Description
Writes a typed value to the SQL-backed variable store (SQLite or MySQL, per `Storage.Type` in
config.yml), scoped globally (shared server-wide, the default — suited to scoreboard-style stats
like `score_red`), per-player, or per-skill-caster (any entity, not just players).

Writes are cached in memory immediately and persisted asynchronously, so this never blocks the
calling skill.


## Attributes
| Attribute | Aliases | Description                                                       | Default |
|-----------|---------|-------------------------------------------------------------------------|---------|
| var       |         | The variable name                                                        | none (required) |
| val       | value   | The value to store                                                       | (empty) |
| type      |         | `STRING`, `INT`, `FLOAT`, or `BOOL` — governs how `addsql` parses it later | STRING  |
| scope     |         | `global` (shared server-wide), `player` (per-caster, players only), `skill` (per-caster, any entity), or `custom` (an arbitrary shared group — see `group=` below) | global  |
| group     |         | Group name for `scope=custom` (e.g. a quest party ID) — supports placeholders like `<skill.var.x>`, so every caster that resolves to the SAME group name shares the same value. Required when `scope=custom`. | (none) |


## Examples
```yaml
SetRedScore:
  Skills:
  - setsql{var=score_red;val=27;type=FLOAT} @trigger
```

```yaml
SetPlayerCoins:
  Skills:
  - setsql{var=coins;val=100;type=INT;scope=player} @trigger
```

```yaml
# Every member of the same quest party shares ONE progress value.
SetPartyQuestProgress:
  Skills:
  - setsql{var=quest_progress;val=3;type=INT;scope=custom;group=<skill.var.party_id>} @trigger
```


## Aliases
None.


## See Also
- [getsql](Skills-Mechanics-getsql) — read a variable into a skill variable.
- [unsetsql](Skills-Mechanics-unsetsql) — delete a variable.
- [addsql](Skills-Mechanics-addsql) — add to/subtract from a numeric variable.
- [setmongo](Skills-Mechanics-setmongo) / [setredis](Skills-Mechanics-setredis) — same shape, MongoDB/Redis-backed.
