## Description
Checks a mob's per-mob applicability override for a MythicEnchants enchantment. The API's
override lookup is 3-state (`true` = force-enabled, `false` = force-disabled, no value = no
override/vanilla behaviour), and `state=` selects which of those to require.


## Attributes
| Attribute | Aliases | Description                                                                     | Default |
|-----------|---------|------------------------------------------------------------------------------------|---------|
| mob       |         | The uppercase internal MythicMobs mob name                                         | none (required) |
| enchant   |         | The enchantment's namespaced id                                                    | none (required) |
| state     |         | Which override state to require — `true`, `false`, or `any` (true when ANY override is defined, regardless of its value) | any |


## Examples
```yaml
Skills:
- message{m="This mob force-blocks Reinforced."} ?menchmobenchantoverride{mob=SKELETON_KING;enchant=mythicenchants:reinforced;state=false} @trigger
```

```yaml
Skills:
- message{m="This mob has an override for Reinforced."} ?menchmobenchantoverride{mob=SKELETON_KING;enchant=mythicenchants:reinforced} @trigger
```


## Aliases
None.
