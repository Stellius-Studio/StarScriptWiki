## Description
True if the thrown egg is going to hatch. Only meaningful inside a skill bound to the
[eggThrow](Skills-Triggers-eggThrow) trigger — it reads the `event-hatching` skill variable that trigger exposes.


## Attributes
None.


## Examples
```yaml
Skills:
- message{m="egg will hatch"} ?eggwillhatch @trigger ~onEggThrow
```


## Aliases
None.


## See Also
- [eggThrow](Skills-Triggers-eggThrow) — the trigger this reads from. Supports `hatching=`/`hatchtype=`/`numhatches=`
  config to override hatch behavior directly.
