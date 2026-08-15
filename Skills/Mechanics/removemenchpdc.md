## Description
Removes a plugin-namespaced PDC value from the caster's or targeted entity's item.


## Attributes
| Attribute | Aliases | Description                                                                     | Default |
|-----------|---------|------------------------------------------------------------------------------------|---------|
| key       |         | The PDC key to remove                                                              | none (required) |
| slot      |         | Which equipment slot's item to modify — `hand`, `offhand`, `head`, `chest`, `legs`, `feet` | hand |


## Examples
```yaml
Skills:
- removemenchpdc{key=owner} @trigger
```


## Aliases
None.
