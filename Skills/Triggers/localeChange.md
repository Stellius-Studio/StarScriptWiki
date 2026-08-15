## Description
Fires when a player's client locale changes (`PlayerLocaleChangeEvent`).


## Config
None.


## Skill Variables
| Variable       | Description                |
|------------------|-------------------------------|
| `event-locale`     | The new locale (e.g. `en_us`)   |


## Examples
```yaml
Skills:
- message{m="<aqua>Locale changed to <skill.var.event-locale>"} @trigger ~onLocaleChange
```
