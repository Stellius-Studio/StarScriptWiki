## Description
Fires when a message is broadcast to the server (`BroadcastMessageEvent`).

Note: this event does not fire when no players are online (Bukkit skips it if the recipient set
would be empty) — it cannot be observed on a headless/empty server.


## Config
| Attribute | Description                              | Default |
|-----------|------------------------------------------------|---------|
| contains  | Only fire if the broadcast message contains this substring | any     |


## Skill Variables
| Variable       | Description             |
|------------------|------------------------------|
| `event-message`    | The plain-text broadcast message |


## Examples
```yaml
Skills:
- log{m="Broadcast: <skill.var.event-message>"} @trigger ~onBroadcast
```
