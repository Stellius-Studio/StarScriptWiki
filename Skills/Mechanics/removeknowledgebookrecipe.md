## Description
Removes a recipe id from the caster's/target's main-hand knowledge book item. No-op if the
main-hand item isn't a knowledge book. Registered together with `addknowledgebookrecipe` (same
mechanic class, dispatched by which name it's invoked under) — see
[addknowledgebookrecipe](Skills-Mechanics-addknowledgebookrecipe) for the add equivalent and
full field reference.


## Attributes
| Attribute | Aliases | Description             | Default |
|-----------|---------|-------------------------------|---------|
| id        |         | The recipe's namespaced key      | none (required) |


## Examples
```yaml
Skills:
- removeknowledgebookrecipe{id=myplugin:fancy_recipe} @trigger
```


## Aliases
None.
