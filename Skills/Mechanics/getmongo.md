## Description
Reads a MongoDB-backed variable and exposes it as a skill variable, so later `Skills:` lines in
the same cast chain can read it via `<skill.var.NAME>`.

Requires `Storage.Mongo.Enabled: true` in config.yml. If Mongo isn't enabled or failed to
connect, this returns `INVALID_CONFIG`.


## Attributes
| Attribute | Aliases | Description                                                | Default |
|-----------|---------|----------------------------------------------------------------|---------|
| var       |         | The variable name to read                                       | none (required) |
| as        | var_out | The skill variable name to store the result in                  | same as `var` |
| default   |         | Fallback value if the variable is unset                         | (empty) |
| scope     |         | `global`, `player`, `skill`, or `custom` (an arbitrary shared group — see `group=` below) — must match how it was written | global  |
| group     |         | Group name for `scope=custom` (e.g. a quest party ID) — supports placeholders like `<skill.var.x>`, so every caster that resolves to the SAME group name shares the same value. Required when `scope=custom`. | (none) |


## Examples
```yaml
ReadRedScore:
  Skills:
  - getmongo{var=score_red;default=0} @trigger
  - message{m="<red>Red team score: <skill.var.score_red>"} @trigger
```

```yaml
# Read the quest progress value shared by every member of the same party.
ReadPartyQuestProgress:
  Skills:
  - getmongo{var=quest_progress;default=0;scope=custom;group=<skill.var.party_id>} @trigger
  - message{m="<aqua>Party quest progress: <skill.var.quest_progress>"} @trigger
```


## Aliases
None.


## See Also
- [setmongo](Skills-Mechanics-setmongo) — write a value.
- [getsql](Skills-Mechanics-getsql) / [getredis](Skills-Mechanics-getredis) — same shape, SQL/Redis-backed.
