## Description
Sets an item's consumption behavior — how long it takes to eat/drink, its use animation,
sound, particles, and any consume effects applied on finish.


## Attributes
| Attribute | Aliases | Description                                                                      | Default |
|-----------|---------|------------------------------------------------------------------------------------|---------|
| slot      |         | Which equipment slot to affect: `hand` (default), `offhand`, `head`, `chest`, `legs`, `feet` | hand    |
| seconds   |         | Time in seconds to fully consume the item                                          | 1.6     |
| animation |         | Use animation: `none`, `eat`, `drink`, `block`, `bow`, `spear`, `crossbow`, `spyglass`, `toothorn`, `brush` | eat |
| sound     |         | Namespaced sound key played while consuming                                        | minecraft:entity.generic.eat |
| particles |         | Whether consume particles are shown                                                | true    |
| effects   |         | `;`-delimited consume effects run on finish — see below                            | none    |

**`effects=` entry syntax** (one or more `;`-separated entries, each starting with a `kind:` tag):
- `apply:TYPE,durationTicks,amplifier[,probability]` — apply a potion effect
- `remove:TYPE1,TYPE2,...` — remove the given effect types
- `clear` — clear all status effects
- `teleport:diameter` — teleport the consumer randomly within a diameter
- `sound:namespaced:key` — play a sound


## Examples
```yaml
MakeHealingPotionFood:
  Skills:
  - consumablecomponent{seconds=1.0;animation=drink;effects="apply:regeneration,100,1;sound:minecraft:entity.generic.drink"} @self
```

```yaml
MakeCleansingBerry:
  Skills:
  - consumablecomponent{animation=eat;effects="clear;teleport:8"} @self
```


## Aliases
None.
