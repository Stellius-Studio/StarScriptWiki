## Description
Removes one recipe by id, or every recipe on the server.


## Attributes
| Attribute    | Aliases | Description                                                                     | Default |
|--------------|---------|-------------------------------------------------------------------------------------|---------|
| id           |         | The recipe's namespaced key to remove — required unless `all=true`                    | none    |
| all          |         | `true` removes every recipe instead of one by id                                      | false   |
| vanillaonly  |         | With `all=true`, only strips `minecraft:`-namespaced recipes, re-adding everything else | false   |


## Examples
```yaml
Skills:
- removerecipe{id=minecraft:acacia_boat}
```

```yaml
Skills:
- removerecipe{all=true;vanillaonly=true}
```


## Aliases
None.
