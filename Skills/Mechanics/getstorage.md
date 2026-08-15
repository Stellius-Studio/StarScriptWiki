## Description
Reads a persistent storage value and exposes it as a skill variable, so later `Skills:` lines in
the same cast chain can read it via `<skill.var.NAME>`.


## Attributes
| Attribute | Aliases | Description                                                | Default |
|-----------|---------|----------------------------------------------------------------|---------|
| key       |         | The storage key to read                                         | none (required) |
| var       |         | The skill variable name to store the result in                  | same as `key` |
| default   |         | Fallback value if the key is unset                              | (empty) |
| scope     |         | `player` (per-caster, players only), `skill` (per-caster, any entity), `global` (shared server-wide), or `custom` (an arbitrary shared group — see `group=` below) | player  |
| group     |         | Group name for `scope=custom` (e.g. a quest party ID) — supports placeholders like `<skill.var.x>`, so every caster that resolves to the SAME group name shares the same storage entry. Required when `scope=custom`. | (none) |


## Examples
```yaml
ReadPlayerCoins:
  Skills:
  - getstorage{key=coins;var=coins;default=0} @trigger
  - message{m="<aqua>You have <skill.var.coins> coins"} @trigger
```

```yaml
# Read the quest progress value shared by every member of the same party.
ReadPartyQuestProgress:
  Skills:
  - getstorage{key=quest_progress;var=progress;default=0;scope=custom;group=<skill.var.party_id>} @trigger
  - message{m="<aqua>Party quest progress: <skill.var.progress>"} @trigger
```


## Aliases
None.


## See Also
- [setstorage](Skills-Mechanics-setstorage) — write a value to storage.
