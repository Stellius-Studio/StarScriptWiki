## Description
Opens the target player's real inventory to the caster — cast with no target, opens the
caster's own inventory to themself. This is the real, live inventory object (not a copy), so
edits made in `edit=true` mode apply directly and instantly, the same as any Bukkit-native
shared container. Useful as a moderation tool (view/edit a player's items remotely).


## Attributes
| Attribute | Aliases | Description                                              | Default |
|-----------|---------|----------------------------------------------------------------|---------|
| edit      |         | `true` allows the caster to move/take/place items; `false` cancels every click (view-only) | false |


## Examples
```yaml
Skills:
- openplayerinventory @PlayerByName{name=<trigger.arg1>} @trigger
```

```yaml
Skills:
- openplayerinventory{edit=true} @PlayerByName{name=<trigger.arg1>} @trigger
```


## Aliases
None.
