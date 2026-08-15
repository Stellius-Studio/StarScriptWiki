## Description
Sets a shulker-box-like item's stored contents (the `CONTAINER` data component).


## Attributes
| Attribute | Aliases | Description                                                              | Default |
|-----------|---------|----------------------------------------------------------------------------------|---------|
| slot      |         | Which equipment slot to affect: `hand` (default), `offhand`, `head`, `chest`, `legs`, `feet` | hand    |
| items     |         | CSV of material names, one stack of each stored inside the container             | none (required) |


## Examples
```yaml
PreloadShulkerBox:
  Skills:
  - containercomponent{items="DIAMOND,DIAMOND,EMERALD"} @self
```


## Aliases
None.
