## Description
Fires when a player sends a chat message (`AsyncChatEvent`).


## Config
| Attribute  | Description                                         | Default |
|------------|----------------------------------------------------------|---------|
| startswith | Only fire if the message starts with this text               | any     |
| contains   | Only fire if the message contains this text                  | any     |
| matches    | Only fire if the message matches this regex                  | any     |

All filters that are set must pass for the trigger to fire.


## Skill Variables
| Variable        | Description               |
|-------------------|---------------------------------|
| `event-message`    | The plain-text chat message       |


## Examples
```yaml
Skills:
- message{m="<light_purple>Hi there, <trigger.name>!"} @trigger ~onChat{startsWith=!hello}
```
