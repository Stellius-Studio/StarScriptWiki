## Description
Pardons (unbans) a player by name or IP.


## Attributes
| Attribute | Aliases | Description                                              | Default |
|-----------|---------|------------------------------------------------------------|---------|
| ip        |         | If `true`, pardons the player's IP address instead of their profile | false   |


## Examples
```yaml
UnbanPlayer:
  Skills:
  - pardon @trigger
```

```yaml
UnbanIp:
  Skills:
  - pardon{ip=true} @trigger
```


## Aliases
- [x] unban
