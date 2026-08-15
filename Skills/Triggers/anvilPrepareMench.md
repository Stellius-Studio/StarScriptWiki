## Description
Fires when the vanilla anvil recomputes its result item for a MythicEnchants-tracked combine
(`MenchAnvilPrepareEvent`). Not cancellable. A skill bound to this trigger can call
[setanvilresult](Skills-Mechanics-setanvilresult) to override the computed result item while the
event is still in-flight — same "mutate before commit" shape as the `prepareEnchant` trigger.


## Config
None.


## Skill Variables
| Variable      | Description                                             |
|---------------|--------------------------------------------------------------|
| `event-left`    | The anvil's left input item's material name, if present        |
| `event-right`   | The anvil's right input item's material name, if present       |
| `event-result`  | The anvil's currently computed result item's material name, if present |


## Examples
```yaml
Skills:
- message{m="<gray>Anvil result: <skill.var.event-result>"} @trigger ~onAnvilPrepareMench
```

```yaml
Skills:
- setanvilresult{item=NETHERITE_SWORD} @trigger ~onAnvilPrepareMench{left=NETHERITE_SWORD}
```
