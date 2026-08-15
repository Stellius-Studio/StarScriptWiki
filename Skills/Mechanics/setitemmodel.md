## Description
Overrides an item's client-side model key, independent of its custom model data.


## Attributes
| Attribute | Aliases | Description                                                              | Default |
|-----------|---------|----------------------------------------------------------------------------------|---------|
| slot      |         | Which equipment slot to affect: `hand` (default), `offhand`, `head`, `chest`, `legs`, `feet` | hand    |
| model     |         | Namespaced model key (e.g. `mynamespace:custom_sword`)                           | none (required) |


## Examples
```yaml
MakeResourcePackSword:
  Skills:
  - setitemmodel{model="mynamespace:custom_sword"} @self
```


## Aliases
None.
