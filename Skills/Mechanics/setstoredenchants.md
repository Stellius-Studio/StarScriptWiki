## Description
Sets an enchanted book's stored enchantments (the `STORED_ENCHANTMENTS` component).


## Attributes
| Attribute | Aliases | Description                                                              | Default |
|-----------|---------|----------------------------------------------------------------------------------|---------|
| slot      |         | Which equipment slot to affect: `hand` (default), `offhand`, `head`, `chest`, `legs`, `feet` | hand    |
| enchants  |         | `;`-delimited `key,level` pairs (e.g. `sharpness,5;unbreaking,3`)                | none (required) |


## Examples
```yaml
MakeMaxedEnchantedBook:
  Skills:
  - setstoredenchants{enchants="sharpness,5;unbreaking,3;mending,1"} @self
```


## Aliases
None.
