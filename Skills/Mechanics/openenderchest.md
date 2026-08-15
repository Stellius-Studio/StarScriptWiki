## Description
Opens the target player's real enderchest to the caster — cast with no target, opens the
caster's own enderchest to themself. This is the real, live enderchest object (not a copy), so
edits made in `edit=true` mode apply directly and instantly. Useful as a moderation tool
(view/edit a player's enderchest remotely).


## Attributes
| Attribute | Aliases | Description                                              | Default |
|-----------|---------|----------------------------------------------------------------|---------|
| edit      |         | `true` allows the caster to move/take/place items; `false` cancels every click (view-only) | false |


## Examples
```yaml
Skills:
- openenderchest @PlayerByName{name=<trigger.arg1>} @trigger
```


## Aliases
None.
