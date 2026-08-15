## Description
Sets a firework rocket item's flight duration and the explosion effects it launches with.


## Attributes
| Attribute      | Aliases | Description                                                              | Default |
|-----------------|---------|----------------------------------------------------------------------------------|---------|
| slot            |         | Which equipment slot to affect: `hand` (default), `offhand`, `head`, `chest`, `legs`, `feet` | hand    |
| flightduration  |         | Flight duration, clamped 0-255                                                   | 1       |
| explosions      |         | `;`-delimited explosion entries — see below                                      | none    |

**`explosions=` entry syntax**: `;`-delimited `shape:colors:fadecolors:trail:twinkle` entries,
where `shape` is one of `ball`, `largeball`, `star`, `creeper`, `burst`; `colors`/`fadecolors` are
`,`-separated hex `RRGGBB` colors; and `trail`/`twinkle` are `true`/`false`.


## Examples
```yaml
MakeCelebrationRocket:
  Skills:
  - fireworkscomponent{flightduration=2;explosions="star:FF0000,FFD700:FFFFFF:true:true;burst:00FF00::false:false"} @self
```


## Aliases
None.
