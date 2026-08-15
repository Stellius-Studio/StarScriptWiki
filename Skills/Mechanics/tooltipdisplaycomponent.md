## Description
Hides an item's whole tooltip, or hides individual data-component lines from it (e.g. hiding
the enchantment list while keeping the rest of the tooltip visible).


## Attributes
| Attribute        | Aliases | Description                                                          | Default |
|-------------------|---------|-----------------------------------------------------------------------------|---------|
| slot              |         | Which equipment slot to affect: `hand` (default), `offhand`, `head`, `chest`, `legs`, `feet` | hand    |
| hidetooltip       |         | Whether the whole tooltip is hidden                                         | false   |
| hiddencomponents  |         | CSV of data-component registry keys to hide from the tooltip (e.g. `minecraft:trim`) | none |


## Examples
```yaml
HideEnchantmentsFromTooltip:
  Skills:
  - tooltipdisplaycomponent{hiddencomponents="minecraft:enchantments,minecraft:trim"} @self
```


## Aliases
None.
