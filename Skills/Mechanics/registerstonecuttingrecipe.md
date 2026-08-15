## Description
Registers a real vanilla stonecutter recipe — shows up in the real stonecutter UI and
StarScript's own `Stonecutter:` GUI regions (which now also fall back to real vanilla
stonecutting recipes, appended after any script-declared matches).


## Attributes
| Attribute   | Aliases | Description                          | Default |
|-------------|---------|--------------------------------------------|---------|
| id          |         | The recipe's namespaced key                  | none (required) |
| result      |         | The output item token                        | none (required) |
| ingredient  |         | The input item token                         | none (required) |
| group       |         | Groups recipes together in the recipe book    | none    |


## Examples
```yaml
Skills:
- registerstonecuttingrecipe{id=myplugin:cut_diamond;result=DIAMOND;ingredient=DIAMOND_ORE}
```


## Aliases
None.
