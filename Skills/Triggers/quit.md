## Description
Fires when a player leaves the server (`PlayerQuitEvent`).


## Config
None.


## Skill Variables
| Variable        | Description         |
|-------------------|--------------------------|
| `event-message`    | The quit message text     |


## Examples
```yaml
Skills:
- broadcast{m="<gray><trigger.name> left the server."} @trigger ~onQuit
```


## See Also
- [join](Skills-Triggers-join) — the login equivalent.
