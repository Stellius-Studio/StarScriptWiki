## Description
Controls an Allay's duplication ability — set/reset its duplication cooldown, toggle whether it's
allowed to duplicate at all, or trigger an immediate duplication.

`duplicate=true` fires a real `CreatureSpawnEvent`; if that spawn is cancelled (by another
plugin), the mechanic returns an invalid-target result.


## Attributes
| Attribute    | Aliases | Description                                                  | Default |
|--------------|---------|------------------------------------------------------------------|---------|
| cooldown     |         | Sets the Allay's duplication cooldown, in ticks                  | unset   |
| reset        |         | If `true`, resets the duplication cooldown instead of setting it | false   |
| canduplicate |         | Toggles whether the Allay is allowed to duplicate at all          | unset   |
| duplicate    |         | If `true`, triggers an immediate duplication                     | false   |


## Examples
```yaml
BoostAllayDupe:
  Skills:
  - allayduplication{cooldown=200} @target
```

```yaml
ForceAllayDuplicateNow:
  Skills:
  - allayduplication{duplicate=true} @target
```

```yaml
DisableAllayDuplication:
  Skills:
  - allayduplication{canduplicate=false} @target
```


## Aliases
None.
