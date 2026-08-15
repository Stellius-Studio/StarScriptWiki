## Description
Sets an item's equip behavior: which slot it equips to, its equip sound, and whether it's
dispensable/swappable/damages on hurt.


## Attributes
| Attribute     | Aliases | Description                                                                 | Default |
|---------------|---------|------------------------------------------------------------------------------------|---------|
| slot          |         | Which equipment slot to affect: `hand` (default), `offhand`, `head`, `chest`, `legs`, `feet` | hand    |
| equipslot     |         | Slot this item equips to when worn: `head`, `chest`, `legs`, `feet`, `hand`, `offhand`, `body` | hand (required) |
| equipsound    |         | Namespaced sound key played on equip                                               | none    |
| assetid       |         | Namespaced asset ID for the equip model                                            | none    |
| dispensable   |         | Whether a dispenser can equip this item onto a mob                                 | true    |
| swappable     |         | Whether right-clicking swaps this item into the slot                               | true    |
| damageonhurt  |         | Whether the item takes durability damage when its wearer is hurt                   | true    |
| cameraoverlay |         | Namespaced key for a camera overlay texture (e.g. pumpkin overlay)                 | none    |


## Examples
```yaml
MakeCustomHelmet:
  Skills:
  - equippablecomponent{equipslot=head;equipsound="minecraft:item.armor.equip_iron";damageonhurt=false} @self
```


## Aliases
None.
