## Description
Registers a real vanilla shaped or shapeless crafting recipe — it shows up in the actual
crafting table/recipe book, not just StarScript's own `Workbench:` GUI regions (which already
fall back to real vanilla recipes automatically). Item fields accept the same token vocabulary
as the GUI-recipe system: a bare/namespaced vanilla material (`IRON_INGOT`,
`minecraft:iron_ingot`), or a prefixed custom item id (`MythicItem:some_id`, `Crucible:some_id`,
`Nexo:some_id`, `ItemsAdder:some_id`).


## Attributes
| Attribute    | Aliases | Description                                                                      | Default |
|--------------|---------|-------------------------------------------------------------------------------------|---------|
| id           |         | The recipe's namespaced key                                                           | none (required) |
| result       |         | The output item token                                                                 | none (required) |
| shaped       |         | `true` for a shaped recipe, `false` for shapeless                                     | true    |
| ingredients  |         | CSV of 4 (2x2) or 9 (3x3) item tokens, row-major; blank/`AIR` = empty slot             | none (required) |
| group        |         | Groups recipes together in the recipe book                                            | none    |


## Examples
```yaml
Skills:
- registercraftingrecipe{id=myplugin:fancy_stick;result=STICK;shaped=true;ingredients=IRON_INGOT,AIR,AIR,IRON_INGOT}
```

```yaml
Skills:
- registercraftingrecipe{id=myplugin:strong_emerald;result=MythicItem:strong_emerald;shaped=false;ingredients=EMERALD,EMERALD,EMERALD}
```


## Aliases
None.
