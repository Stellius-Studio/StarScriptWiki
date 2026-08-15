## Description
Sets a firework-star-like item's own explosion effect directly — distinct from
[fireworkscomponent](Skills-Mechanics-fireworkscomponent), which is for firework rockets holding
multiple explosions.


## Attributes
| Attribute  | Aliases | Description                                                              | Default |
|------------|---------|----------------------------------------------------------------------------------|---------|
| slot       |         | Which equipment slot to affect: `hand` (default), `offhand`, `head`, `chest`, `legs`, `feet` | hand    |
| shape      |         | Explosion shape: `ball`, `largeball`, `star`, `creeper`, `burst`                  | ball    |
| colors     |         | `,`-separated hex `RRGGBB` colors                                                 | none    |
| fadecolors |         | `,`-separated hex `RRGGBB` fade colors                                            | none    |
| trail      |         | `true`/`false` — whether the explosion leaves a trail                            | none    |
| twinkle    |         | `true`/`false` — whether the explosion twinkles                                   | none    |


## Examples
```yaml
MakeFireworkStar:
  Skills:
  - fireworkexplosioncomponent{shape=star;colors="FF00FF";trail=true;twinkle=true} @self
```


## Aliases
None.
