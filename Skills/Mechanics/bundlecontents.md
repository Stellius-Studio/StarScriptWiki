## Description
Sets, adds to, or removes from a bundle item's contents. Uses the legacy bundle-meta API rather
than a data component.


## Attributes
| Attribute | Aliases | Description                                                              | Default |
|-----------|---------|----------------------------------------------------------------------------------|---------|
| slot      |         | Which equipment slot to affect: `hand` (default), `offhand`, `head`, `chest`, `legs`, `feet` | hand    |
| items     |         | CSV of material names, one stack of each item added/removed/set                  | none (required) |
| mode      |         | `set`, `add`, or `remove`                                                        | set     |


## Examples
```yaml
FillAdventurerBundle:
  Skills:
  - bundlecontents{items="COOKED_BEEF,TORCH,ARROW";mode=set} @self
```


## Aliases
None.
