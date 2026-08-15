## Description
Fires when a player finishes editing a sign (`SignChangeEvent`). The target is the sign block's
location.


## Config
| Attribute | Description                                    | Default |
|-----------|-----------------------------------------------------|---------|
| contains  | Only fire if ANY of the 4 sign lines contains this text  | any     |


## Skill Variables
| Variable          | Description                                                  |
|---------------------|--------------------------------------------------------------------|
| `event-line-1`       | The sign's first line as plain text, empty string if blank             |
| `event-line-2`       | The sign's second line as plain text, empty string if blank            |
| `event-line-3`       | The sign's third line as plain text, empty string if blank             |
| `event-line-4`       | The sign's fourth line as plain text, empty string if blank            |


## Examples
```yaml
Skills:
- message{m="<green>Shop sign created!"} @trigger ~onSignChange{contains=[shop]}
```
