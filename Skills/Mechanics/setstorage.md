## Description
Writes a string value to persistent key-value storage, scoped to the casting player, the
casting entity, the whole server, or an arbitrary shared group.

Writes are cached in memory immediately and persisted to disk asynchronously, so this never blocks
the calling skill.


## Attributes
| Attribute | Aliases | Description                                      | Default |
|-----------|---------|-----------------------------------------------------|---------|
| key       |         | The storage key                                     | none (required) |
| value     |         | The value to store                                   | (empty) |
| scope     |         | `player` (per-caster, players only), `skill` (per-caster, any entity), `global` (shared server-wide), or `custom` (an arbitrary shared group — see `group=` below) | player  |
| group     |         | Group name for `scope=custom` (e.g. a quest party ID) — supports placeholders like `<skill.var.x>`, so every caster that resolves to the SAME group name shares the same storage entry. Required when `scope=custom`. | (none) |


## Examples
```yaml
SetPlayerCoins:
  Skills:
  - setstorage{key=coins;value=100} @trigger
```

```yaml
SetGlobalEventFlag:
  Skills:
  - setstorage{key=serverevent;value=active;scope=global} @trigger
```

```yaml
# Every member of the same quest party shares ONE progress value, keyed by a party ID stored
# earlier in <skill.var.party_id> - regardless of which party member's cast writes it.
SetPartyQuestProgress:
  Skills:
  - setstorage{key=quest_progress;value=3;scope=custom;group=<skill.var.party_id>} @trigger
```


## Aliases
None.


## See Also
- [getstorage](Skills-Mechanics-getstorage) — read a stored value into a skill variable.
- [removestorage](Skills-Mechanics-removestorage) — delete a stored value.
- [incrementstorage](Skills-Mechanics-incrementstorage) — add to/subtract from a numeric stored value.
- [`<script.storage.KEY>`](Skills-Placeholders#scriptstoragekey) and `%starscript_storage_<key>%` —
  read a stored value as a placeholder.
