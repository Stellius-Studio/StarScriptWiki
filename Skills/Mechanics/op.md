## Description
Sets or clears a player's operator status.


## Attributes
| Attribute | Aliases | Description                                  | Default |
|-----------|---------|-------------------------------------------------|---------|
| state     |         | `true` to grant operator status, `false` to revoke | true    |


## Examples
```yaml
GrantOp:
  Skills:
  - op @trigger
```

```yaml
RevokeOp:
  Skills:
  - op{state=false} @trigger
```


## Aliases
None.
