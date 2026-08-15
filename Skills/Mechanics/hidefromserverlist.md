## Description
Removes (or restores) a specific player from the server-list ping's hover list of online players.


## Attributes
| Attribute | Aliases | Description                                  | Default |
|-----------|---------|-----------------------------------------------|---------|
| state     |         | `true` to hide the player, `false` to unhide them | true    |


## Examples
```yaml
HidePlayerFromPing:
  Skills:
  - hidefromserverlist @trigger
```

```yaml
UnhidePlayerFromPing:
  Skills:
  - hidefromserverlist{state=false} @trigger
```


## Aliases
None.
