## Description
Fires when a command is run from the server console (`ServerCommandEvent`).


## Config
| Attribute | Description                                             | Default |
|-----------|--------------------------------------------------------------|---------|
| command   | Only fire if the command name (without arguments) matches      | any     |


## Skill Variables
| Variable      | Description                            |
|-----------------|---------------------------------------------|
| `event-command`   | The command name (without arguments)             |
| `args`            | The command's arguments as a single string         |


## Examples
```yaml
Skills:
- log{m="Console ran: <skill.var.event-command>"} @trigger ~onConsoleCommand
```
