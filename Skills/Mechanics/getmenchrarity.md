## Description
Reads the registered rarity tier id for a MythicEnchants enchantment into a skill variable.
Writes an empty string if the enchantment is unregistered or has no configured rarity.


## Attributes
| Attribute | Aliases | Description                                                    | Default |
|-----------|---------|--------------------------------------------------------------------|---------|
| enchant   |         | The enchantment's namespaced id                                    | none (required) |
| var       |         | The skill variable name to store the rarity tier id into           | rarity |


## Examples
```yaml
Skills:
- getmenchrarity{enchant=mythicenchants:reinforced;var=tier} @trigger
- message{m="Rarity: <skill.var.tier>"} @trigger
```


## Aliases
None.
