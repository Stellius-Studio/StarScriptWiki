## Description
Reads a Redis-backed variable as a number, adds an amount (positive or negative), and writes the
result back. A missing variable is created as `FLOAT` starting from `0`. Fails
(`INVALID_CONFIG`) if the variable already exists but is typed `STRING` or `BOOL` — those aren't
addable.

Requires `Storage.Redis.Enabled: true` in config.yml. If Redis isn't enabled or failed to
connect, this returns `INVALID_CONFIG`.


## Attributes
| Attribute | Aliases | Description                                                    | Default |
|-----------|---------|------------------------------------------------------------------|---------|
| var       |         | The variable name to increment                                     | none (required) |
| a         | amount  | Amount to add (use a negative number to decrement)                  | 1       |
| scope     |         | `global`, `player`, `skill`, or `custom` (an arbitrary shared group — see `group=` below) — must match how it was written | global  |
| group     |         | Group name for `scope=custom` (e.g. a quest party ID) — supports placeholders like `<skill.var.x>`, so every caster that resolves to the SAME group name shares the same value. Required when `scope=custom`. | (none) |


## Examples
```yaml
AddRedScore:
  Skills:
  - addredis{var=score_red;a=1} @trigger
```

```yaml
# Every member of the same quest party increments ONE shared counter.
AddPartyQuestProgress:
  Skills:
  - addredis{var=quest_progress;a=1;scope=custom;group=<skill.var.party_id>} @trigger
```


## Aliases
- [x] subtractredis


## See Also
- [setredis](Skills-Mechanics-setredis) — write a value with an explicit type.
- [addsql](Skills-Mechanics-addsql) / [addmongo](Skills-Mechanics-addmongo) — same shape, SQL/MongoDB-backed.
