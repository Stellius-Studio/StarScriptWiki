## Description
Sets a potion-like item's contents: base potion type, custom color/name, and custom effects.


## Attributes
| Attribute      | Aliases | Description                                                              | Default |
|-----------------|---------|----------------------------------------------------------------------------------|---------|
| slot            |         | Which equipment slot to affect: `hand` (default), `offhand`, `head`, `chest`, `legs`, `feet` | hand    |
| potion          |         | Base potion type name (e.g. `STRONG_HEALING`)                                    | none    |
| customcolor     |         | Hex color (`RRGGBB`) for the potion swirl                                        | none    |
| customname      |         | Custom potion name                                                               | none    |
| customeffects   |         | `;`-delimited `TYPE,durationTicks,amplifier` triples                             | none    |


## Examples
```yaml
MakeCustomBrew:
  Skills:
  - potioncontentscomponent{potion=WATER;customname="Elixir of Fortitude";customcolor="8A2BE2";customeffects="strength,1200,1;fire_resistance,1200,0"} @self
```


## Aliases
None.
