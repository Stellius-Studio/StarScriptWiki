## Description
Manipulates a Warden's anger toward a target, or points it at a sensed disturbance location.

`anger=`/`increase=`/`clear=` all act on the anger the Warden holds toward the skill's resolved
target entity — they require a target to resolve. `disturb=true` calls the Warden's disturbance-
sensing behavior against the skill's target location (or the caster's own location, when no
location target is given).


## Attributes
| Attribute | Aliases | Description                                                  | Default |
|-----------|---------|------------------------------------------------------------------|---------|
| anger     |         | Sets the Warden's anger level toward the target (requires a target) | unset   |
| increase  |         | Increases the Warden's anger level toward the target by this amount | unset   |
| clear     |         | If `true`, clears the Warden's anger toward the target             | false   |
| disturb   |         | If `true`, points the Warden at the resolved disturbance location   | false   |


## Examples
```yaml
AngerTheWarden:
  Skills:
  - wardendisturbance{anger=50} @target
```

```yaml
CalmTheWarden:
  Skills:
  - wardendisturbance{clear=true} @target
```

```yaml
SenseDisturbance:
  Skills:
  - wardendisturbance{disturb=true} @target
```


## Aliases
None.
