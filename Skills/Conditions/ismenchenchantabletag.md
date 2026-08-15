## Description
True if `ref=` (e.g. `#minecraft:enchantable/sword`) is a recognized enchantable tag for the
running Minecraft version.


## Attributes
| Attribute | Aliases | Description                 | Default |
|-----------|---------|--------------------------------|---------|
| ref       |         | The enchantable tag reference to check | none (required) |


## Examples
```yaml
Skills:
- message{m="Unknown enchantable tag."} ?ismenchenchantabletag{ref=#minecraft:enchantable/sword;NOT} @trigger
```


## Aliases
None.
