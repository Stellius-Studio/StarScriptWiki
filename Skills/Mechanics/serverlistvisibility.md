## Description
Globally hides the player count/hover list in the server-list ping (clients show `???` for the
player count), or restores it.


## Attributes
| Attribute | Aliases | Description                                    | Default |
|-----------|---------|---------------------------------------------------|---------|
| state     |         | `true` to hide the player count/hover list, `false` to restore it | true    |


## Examples
```yaml
HidePlayerCount:
  Skills:
  - serverlistvisibility @trigger
```

```yaml
ShowPlayerCount:
  Skills:
  - serverlistvisibility{state=false} @trigger
```


## Aliases
None.
