## Description
Fires when a player joins the server (`PlayerJoinEvent`), while their connection/client is still
settling in. A `message{...}` (or similar) line on `~onJoin` with no delay can fire correctly but
never actually show up for the player — add `delay=20` (1 second) to give the client a moment;
see [Universal trigger token options](Skills-Scripts#universal-trigger-token-options).


## Config
| Attribute | Description                                              | Default |
|-----------|--------------------------------------------------------------|---------|
| firstjoin | Only fire if this is the player's first ever join on the server | false   |


## Skill Variables
| Variable        | Description                              |
|-------------------|-----------------------------------------------|
| `event-message`    | The join message text, empty if none            |


## Examples
```yaml
Skills:
- message{m="<green>Welcome back, <trigger.name>!"} @trigger ~onJoin{delay=20}
```

```yaml
Skills:
- message{m="<gold>Welcome to the server, <trigger.name>! Type /help to get started."} @trigger ~onJoin{firstjoin=true;delay=20}
```


## See Also
- [quit](Skills-Triggers-quit) — the logout equivalent.
