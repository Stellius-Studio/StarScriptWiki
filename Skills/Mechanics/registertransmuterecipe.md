## Description
Registers a real vanilla transmute recipe — changes an input item's material while preserving
its other data (used by vanilla for dyeing shulker boxes). Only `result=`'s material is used;
its other data is discarded in favor of the input item's own data.


## Attributes
| Attribute  | Aliases | Description                                              | Default |
|------------|---------|----------------------------------------------------------------|---------|
| id         |         | The recipe's namespaced key                                       | none (required) |
| result     |         | An item token — only its material is used                         | none (required) |
| input      |         | The item token whose data is preserved into the result             | none (required) |
| material   |         | The item token applied like a dye                                  | none (required) |
| group      |         | Groups recipes together in the recipe book                        | none    |


## Examples
```yaml
Skills:
- registertransmuterecipe{id=myplugin:better_swords;result=NETHERITE_SWORD;input=minecraft item tag:minecraft:swords;material=NETHERITE_INGOT}
```


## Aliases
None.
