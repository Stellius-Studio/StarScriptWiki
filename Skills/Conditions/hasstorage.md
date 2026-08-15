## Description
True if a persistent storage entry (the same store behind
[setstorage](Skills-Mechanics-setstorage)) is set — or, with `value=`, true only if it equals a
given value. Reads storage directly, so you don't need a separate
[getstorage](Skills-Mechanics-getstorage) + `CompareValues` pair just to gate a line on stored
state.

With no `value=`: true if the key is set to any non-blank value ("does this exist at all").
With `value=`: true only if the stored value equals it (case-insensitive by default).


## Attributes
| Attribute  | Aliases | Description                                                             | Default |
|------------|---------|--------------------------------------------------------------------------|---------|
| key        |         | The storage key to check                                                    | none (required) |
| value      |         | If set, the stored value must equal this (placeholders resolved fresh on every check, e.g. `<skill.var.x>`) | (unset — presence-only check) |
| ignorecase |         | If `true`, the `value=` comparison is case-insensitive (only applies when `value=` is set) | true |
| scope      |         | `player` (per-caster, players only), `skill` (per-caster, any entity), `global` (shared server-wide), or `custom` (an arbitrary shared group — see `group=` below) | player  |
| group      |         | Group name for `scope=custom` (e.g. a quest party ID) — supports placeholders like `<skill.var.x>`, so every caster that resolves to the SAME group name reads the SAME storage entry. Required when `scope=custom`. | (none) |


## Examples
```yaml
# Presence check - has the player started this quest at all?
Skills:
- message{m="<green>Quest in progress!"} ?hasstorage{key=quest_started} @trigger

# Value check - is the quest specifically done?
Skills:
- message{m="<gold>Quest already complete!"} ?hasstorage{key=quest_state;value=done} @trigger

# Custom-scoped check - is this player's quest party's shared quest done?
Skills:
- message{m="<gold>Your party finished it!"} ?hasstorage{key=quest_state;value=done;scope=custom;group=<skill.var.party_id>} @trigger
```


## Aliases
`storageequals`.


## See Also
- [setstorage](Skills-Mechanics-setstorage) — write a value to storage (also documents `scope=`/`group=`).
- [getstorage](Skills-Mechanics-getstorage) — read a stored value into a skill variable when you
  need the actual value, not just a yes/no check.
- [removestorage](Skills-Mechanics-removestorage) — delete a stored value.
