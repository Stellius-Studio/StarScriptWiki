## Description
Sets the item this item turns into after being fully used or consumed (e.g. a full milk bucket
leaving behind an empty bucket).


## Attributes
| Attribute | Aliases | Description                                                              | Default |
|-----------|---------|----------------------------------------------------------------------------------|---------|
| slot      |         | Which equipment slot to affect: `hand` (default), `offhand`, `head`, `chest`, `legs`, `feet` | hand    |
| item      |         | Material name of the resulting remainder item                                    | none (required) |


## Examples
```yaml
MakeCustomBrew:
  Skills:
  - setuseremainder{item="GLASS_BOTTLE"} @self
```


## Aliases
None.
