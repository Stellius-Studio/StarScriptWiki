## Description
True if the caster (a player) has discovered/unlocked the given recipe.


## Attributes
| Attribute | Aliases | Description             | Default |
|-----------|---------|-------------------------------|---------|
| id        |         | The recipe's namespaced key      | none (required) |


## Examples
```yaml
Skills:
- message{m="You already know this recipe!"} ?hasdiscoveredrecipe{id=myplugin:fancy_recipe} @trigger
```


## Aliases
None.
