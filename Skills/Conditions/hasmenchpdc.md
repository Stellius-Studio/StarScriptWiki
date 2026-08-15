## Description
True if the caster's item has a plugin-namespaced PDC value stored under the given key (see
[setmenchpdc](Skills-Mechanics-setmenchpdc)).


## Attributes
| Attribute | Aliases | Description                                                                | Default |
|-----------|---------|------------------------------------------------------------------------------|---------|
| key       |         | The PDC key to check                                                         | none (required) |
| slot      |         | Which equipment slot's item to check — `hand`, `offhand`, `head`, `chest`, `legs`, `feet` | hand |


## Examples
```yaml
Skills:
- message{m="This item has an owner tag."} ?hasmenchpdc{key=owner} @trigger
```


## Aliases
None.
