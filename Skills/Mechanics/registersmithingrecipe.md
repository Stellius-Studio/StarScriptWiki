## Description
Registers a real vanilla smithing-table transform recipe (template + base + addition → result,
same shape as netherite upgrades).


## Attributes
| Attribute  | Aliases | Description                                                          | Default |
|------------|---------|---------------------------------------------------------------------------|---------|
| id         |         | The recipe's namespaced key                                                | none (required) |
| result     |         | The output item token                                                      | none (required) |
| template   |         | The template-slot item token                                               | none (required) |
| base       |         | The base-slot item token                                                   | none (required) |
| addition   |         | The addition-slot item token; omit for an empty-choice addition slot        | empty choice |
| copynbt    |         | Whether to copy the base item's data onto the result                       | true    |


## Examples
```yaml
Skills:
- registersmithingrecipe{id=myplugin:fire_sword;result=MythicItem:fire_sword;template=PAPER;base=DIAMOND_SWORD;addition=BLAZE_POWDER}
```


## Aliases
None.
