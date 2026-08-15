## Description
Locks (removes from the recipe book) a recipe for the caster's/target's player. Registered
together with `discoverrecipe` (same mechanic class, dispatched by which name it's invoked
under) — see [discoverrecipe](Skills-Mechanics-discoverrecipe) for the unlock equivalent and
full field reference.


## Attributes
| Attribute | Aliases | Description             | Default |
|-----------|---------|-------------------------------|---------|
| id        |         | The recipe's namespaced key      | none (required) |


## Examples
```yaml
Skills:
- undiscoverrecipe{id=minecraft:golden_shovel} @trigger
```


## Aliases
None.
