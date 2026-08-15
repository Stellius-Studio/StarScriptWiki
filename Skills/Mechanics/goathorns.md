## Description
Controls a Goat's horns and screaming flag, and can trigger a real ram attack against the skill's
resolved target.

`ram=true` rams the skill's own target/trigger entity if one resolves as a living entity — this
isn't a boolean flag on the Goat itself, it's a real triggered action.


## Attributes
| Attribute | Aliases | Description                                              | Default |
|-----------|---------|--------------------------------------------------------------|---------|
| left      |         | Sets whether the Goat has its left horn                      | unset   |
| right     |         | Sets whether the Goat has its right horn                     | unset   |
| screaming |         | Sets the Goat's screaming-variant flag                       | unset   |
| ram       |         | If `true`, rams the resolved target (requires a living entity target) | false   |


## Examples
```yaml
RemoveGoatHorns:
  Skills:
  - goathorns{left=false;right=false} @target
```

```yaml
ScreamingGoat:
  Skills:
  - goathorns{screaming=true} @target
```

```yaml
GoatRamsPlayer:
  Skills:
  - goathorns{ram=true} @target
```


## Aliases
None.
