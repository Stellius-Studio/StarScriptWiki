## Description
True if the given MythicEnchants enchantment's effects are currently enabled (`Options: Enabled:`
in its definition). False if the enchantment is unregistered.


## Attributes
| Attribute | Aliases | Description                 | Default |
|-----------|---------|--------------------------------|---------|
| enchant   |         | The enchantment's namespaced id | none (required) |


## Examples
```yaml
Skills:
- message{m="This enchant is currently disabled."} ?ismenchenabled{enchant=mythicenchants:reinforced;NOT} @trigger
```


## Aliases
None.
