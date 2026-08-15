## Description
Adds a recipe id to the caster's/target's main-hand knowledge book item — giving that book to
a player and letting them read it discovers the recipe for them. No-op if the main-hand item
isn't a knowledge book. Registered together with `removeknowledgebookrecipe` (same mechanic
class, dispatched by which name it's invoked under) — see
[removeknowledgebookrecipe](Skills-Mechanics-removeknowledgebookrecipe) for the removal
equivalent.


## Attributes
| Attribute | Aliases | Description             | Default |
|-----------|---------|-------------------------------|---------|
| id        |         | The recipe's namespaced key      | none (required) |


## Examples
```yaml
Skills:
- addknowledgebookrecipe{id=myplugin:fancy_recipe} @trigger
```


## Aliases
None.
