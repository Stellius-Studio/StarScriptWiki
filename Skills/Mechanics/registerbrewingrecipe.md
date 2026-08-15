## Description
Registers a real vanilla brewing-stand recipe (a `PotionMix`) — shows up in the real brewing
stand. **Note:** StarScript's own `Brewing:` GUI regions do NOT automatically pick up recipes
registered this way (the Paper API used has no way to enumerate registered `PotionMix`es to
match against) — declare the same recipe in the script's own `Recipes:` list under the
`Brewing:` section if you also want it usable in a custom brewing GUI.


## Attributes
| Attribute   | Aliases | Description                                    | Default |
|-------------|---------|------------------------------------------------------|---------|
| id          |         | The recipe's namespaced key                             | none (required) |
| result      |         | The output item token (goes into the 3 bottle slots)     | none (required) |
| ingredient  |         | The top-slot ingredient item token                       | none (required) |
| input       |         | The bottle-slot input item token                         | none (required) |


## Examples
```yaml
Skills:
- registerbrewingrecipe{id=myplugin:brew_glow_diamond;result=DIAMOND;ingredient=GLOWSTONE_DUST;input=POTATO}
```


## Aliases
None.
