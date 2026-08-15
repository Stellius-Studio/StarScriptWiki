## Description
Sends a player to another backend server by name, via the `bungeecord:main` plugin-messaging
channel. Requires a BungeeCord or Velocity proxy in front of the backend servers.

`server=` supports placeholders (e.g. `<skill.var.x>`), resolved against the caster/target at
cast time.


## Attributes
| Attribute | Aliases | Description                                    | Default |
|-----------|---------|---------------------------------------------------|---------|
| server    |         | The name of the backend server to send the player to (as registered on the proxy) | none (required) |


## Examples
```yaml
SendToLobby:
  Skills:
  - connect{server=lobby} @trigger
```


## Aliases
- [x] transfer
