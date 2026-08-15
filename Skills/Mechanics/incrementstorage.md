## Description
Reads a persistent storage value as a number, adds an amount (positive or negative), and writes
the result back. An unset or non-numeric existing value is treated as `0`.


## Attributes
| Attribute | Aliases | Description                                                    | Default |
|-----------|---------|------------------------------------------------------------------|---------|
| key       |         | The storage key to increment                                       | none (required) |
| amount    |         | Amount to add (use a negative number to decrement)                  | 1       |
| var       |         | Optional skill variable to receive the new value                    | (not set) |
| scope     |         | `player` (per-caster, players only), `skill` (per-caster, any entity), `global` (shared server-wide), or `custom` (an arbitrary shared group — see `group=` below) | player  |
| group     |         | Group name for `scope=custom` (e.g. a quest party ID) — supports placeholders like `<skill.var.x>`, so every caster that resolves to the SAME group name shares the same storage entry. Required when `scope=custom`. | (none) |


## Examples
```yaml
AddScore:
  Skills:
  - incrementstorage{key=score;amount=5;var=score} @trigger
  - message{m="<aqua>New score: <skill.var.score>"} @trigger
```

```yaml
SubtractScore:
  Skills:
  - incrementstorage{key=score;amount=-3} @trigger
```

```yaml
# Every member of the same quest party increments ONE shared counter.
AddPartyQuestProgress:
  Skills:
  - incrementstorage{key=quest_progress;amount=1;scope=custom;group=<skill.var.party_id>} @trigger
```


## Aliases
- [x] decrementstorage
