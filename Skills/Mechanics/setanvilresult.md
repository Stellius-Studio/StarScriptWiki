## Description
Overrides the result item of an in-progress vanilla anvil combine while a
[`anvilPrepareMench`](Skills-Triggers-anvilPrepareMench) trigger's skill is executing. Only
meaningful inside a skill bound to that trigger — outside its execution window (e.g. called from
an unrelated skill) this mechanic no-ops and fails.


## Attributes
| Attribute | Aliases | Description                                                                    | Default |
|-----------|---------|--------------------------------------------------------------------------------|---------|
| item      |         | The replacement result item — a vanilla material name or a prefixed custom-item token (e.g. `NETHERITE_SWORD`, `MythicItem:foo`) | none (required) |


## Examples
```yaml
Skills:
- setanvilresult{item=NETHERITE_SWORD} @trigger ~onAnvilPrepareMench{left=NETHERITE_SWORD}
```

```yaml
Skills:
- setanvilresult{item=mythic:cursebreaker_blade} @trigger ~onAnvilPrepareMench
```


## Aliases
None.
