## Description
Deletes a persistent key-value storage entry.


## Attributes
| Attribute | Aliases | Description                                    | Default |
|-----------|---------|---------------------------------------------------|---------|
| key       |         | The storage key to delete                          | none (required) |
| scope     |         | `player` (per-caster, players only), `skill` (per-caster, any entity), `global` (shared server-wide), or `custom` (an arbitrary shared group — see `group=` below) | player  |
| group     |         | Group name for `scope=custom` (e.g. a quest party ID) — supports placeholders like `<skill.var.x>`, so every caster that resolves to the SAME group name shares the same storage entry. Required when `scope=custom`. | (none) |


## Examples
```yaml
ClearPlayerCoins:
  Skills:
  - removestorage{key=coins} @trigger
```

```yaml
# Delete the quest progress value shared by every member of the same party.
ClearPartyQuestProgress:
  Skills:
  - removestorage{key=quest_progress;scope=custom;group=<skill.var.party_id>} @trigger
```


## Aliases
None.


## See Also
- [setstorage](Skills-Mechanics-setstorage) — write a value to storage.
