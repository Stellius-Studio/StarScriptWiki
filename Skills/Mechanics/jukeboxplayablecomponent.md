## Description
Makes a music-disc-like item playable in a jukebox.


## Attributes
| Attribute | Aliases | Description                                                              | Default |
|-----------|---------|----------------------------------------------------------------------------------|---------|
| slot      |         | Which equipment slot to affect: `hand` (default), `offhand`, `head`, `chest`, `legs`, `feet` | hand    |
| song      |         | Namespaced jukebox song key (e.g. `minecraft:13`)                                | none (required) |


## Examples
```yaml
MakeCustomMusicDisc:
  Skills:
  - jukeboxplayablecomponent{song="minecraft:pigstep"} @self
```


## Aliases
None.
