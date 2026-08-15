## Description
True if the caster's inventory has room for the given amount of an item, counting both empty
slots (each worth the item's max stack size) and leftover space in existing partial stacks of the
same item. Unlike [canpickupitems](Skills-Conditions-canpickupitems) (the vanilla "allowed to
pick up items" entity flag), this answers "would giving this item actually fit" — a full
inventory of non-stacking items has no empty slots and no room, while an inventory with a partial
stack has room for however many more fit before the stack caps out.


## Attributes
| Attribute | Aliases | Description                        | Default |
|-----------|---------|------------------------------------|---------|
| item      | i       | The material name to check room for | (empty) |
| amount    | a       | The quantity to check room for      | 1       |


## Examples
```yaml
Skills:
- message{m="you have room for 7 diamonds"} ?caninventoryfit{item=DIAMOND;amount=7} @trigger
- message{m="no room for another totem"} ?!caninventoryfit{i=TOTEM_OF_UNDYING} @trigger
```


## Aliases
None.


## See Also
- [canpickupitems](Skills-Conditions-canpickupitems) — the vanilla "allowed to pick up items" flag, not a capacity check.
