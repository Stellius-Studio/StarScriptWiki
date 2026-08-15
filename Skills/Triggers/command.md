## Description
Fires when a player runs a command (`PlayerCommandPreprocessEvent`).


## Config
| Attribute | Description                                                        | Default |
|-----------|-------------------------------------------------------------------------|---------|
| command   | Comma-separated list of command names to filter on, without the leading `/` | any     |


## Skill Variables
| Variable          | Description                                      |
|---------------------|-------------------------------------------------------|
| `event-command`      | The command name, without the leading `/`               |
| `args`               | Everything after the command name, or empty string if none |


## Examples
```yaml
Skills:
- message{m="<gray>Running /home with args: <skill.var.args>"} @trigger ~onCommand{command=home,sethome}
```
