## Description
Registers a real vanilla furnace/blast furnace/smoker/campfire recipe — shows up in the real
furnace UI and StarScript's own `Furnace:` GUI regions (which already fall back to real vanilla
cooking recipes automatically).


## Attributes
| Attribute   | Aliases | Description                                                | Default |
|-------------|---------|------------------------------------------------------------------|---------|
| id          |         | The recipe's namespaced key                                        | none (required) |
| result      |         | The output item token                                              | none (required) |
| ingredient  |         | The input item token                                               | none (required) |
| type        |         | `furnace`, `blasting`, `smoking`, or `campfire`                    | furnace |
| experience  |         | XP awarded on collecting the output                                | 0       |
| cooktime    |         | Ticks to cook; default is the vanilla value for `type=`              | 200 (furnace) / 100 (blasting/smoking) / 600 (campfire) |
| group       |         | Groups recipes together in the recipe book                         | none    |


## Examples
```yaml
Skills:
- registercookingrecipe{id=myplugin:diamond_from_dirt;result=DIAMOND;ingredient=DIRT;type=furnace}
```

```yaml
Skills:
- registercookingrecipe{id=myplugin:hot_cod;result=MythicItem:hot_cod;ingredient=PUFFERFISH;type=smoking}
```


## Aliases
None.
