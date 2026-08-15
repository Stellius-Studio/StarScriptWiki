## Description
Sets a player-head item's owning profile — name, UUID, and skin texture. Only affects items;
skull blocks/mannequins/players aren't covered.


## Attributes
| Attribute         | Aliases | Description                                                              | Default |
|--------------------|---------|----------------------------------------------------------------------------------|---------|
| slot               |         | Which equipment slot to affect: `hand` (default), `offhand`, `head`, `chest`, `legs`, `feet` | hand    |
| name               |         | Profile name shown for the head                                                  | none    |
| id                 |         | Profile UUID (as a string)                                                       | none    |
| texturevalue       |         | Base64 skin texture blob                                                         | none    |
| texturesignature   |         | Texture signature, only meaningful alongside `texturevalue=`                     | none    |


## Examples
```yaml
MakeCustomHead:
  Skills:
  - profilecomponent{slot=head;name="CustomHead";texturevalue="<base64texture>"} @self
```


## Aliases
None.
