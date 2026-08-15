## Description
Locks or unlocks (adds to the recipe book) a recipe for the caster's/target's player.
Registered together with `undiscoverrecipe` (same mechanic class, dispatched by which name
it's invoked under) — see [undiscoverrecipe](Skills-Mechanics-undiscoverrecipe) for the lock
equivalent.


## Attributes
| Attribute | Aliases | Description             | Default |
|-----------|---------|-------------------------------|---------|
| id        |         | The recipe's namespaced key      | none (required) |


## Examples
```yaml
Skills:
- discoverrecipe{id=myplugin:fancy_diamonds} @trigger
```


## Aliases
None.
