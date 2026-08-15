## Description
Fires when a player throws an egg (`PlayerEggThrowEvent`).

`hatching=`/`hatchtype=`/`numhatches=` let a script force/prevent a hatch and pick what hatches —
Bukkit only exposes this as a one-shot decision on the event itself, so the override happens
directly in this trigger's extractor before skill lines fire.


## Config
| Attribute  | Description                                                       | Default |
|------------|---------------------------------------------------------------------|---------|
| hatching   | Overrides whether the egg hatches (`true`/`false`)                    | vanilla behavior |
| hatchtype  | Overrides the entity type that hatches (e.g. `CHICKEN`)               | vanilla behavior |
| numhatches | Overrides how many entities hatch                                     | vanilla behavior |


## Skill Variables
| Variable          | Description                                  |
|--------------------|--------------------------------------------------|
| `event-hatching`     | Whether the egg is going to hatch (after any override) |


## Examples
```yaml
Skills:
- message{m="<aqua>Force-hatch a chicken!"} @trigger ~onEggThrow{hatching=true;hatchtype=CHICKEN}
```


## See Also
- [eggwillhatch](Skills-Conditions-eggwillhatch) — condition wrapping `event-hatching`.
