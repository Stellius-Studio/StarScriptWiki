## Description
Shows or hides the caster's/target's per-player sidebar. Targets the caster if it's a player,
otherwise the skill's entity target.


## Attributes
| Attribute | Aliases | Description                                          | Default |
|-----------|---------|------------------------------------------------------------|---------|
| state     |         | `on` (show) or `off` (hide); omit to toggle the current state | toggle |


## Examples
```yaml
Skills:
- toggleboard{state=off} @trigger
```

```yaml
Skills:
- toggleboard @trigger
```


## Aliases
None.
