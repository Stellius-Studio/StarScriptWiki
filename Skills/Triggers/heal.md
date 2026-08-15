## Description
Fires when a player regains health (`EntityRegainHealthEvent`).


## Config
| Attribute | Description                                                | Default |
|-----------|----------------------------------------------------------------|---------|
| reason    | Only fire if the regain reason matches (e.g. `REGEN`, `EATING`, `SATIATED`) | any     |


## Skill Variables
| Variable       | Description                     |
|------------------|--------------------------------------|
| `event-amount`     | The amount of health regained          |
| `event-reason`     | The regain reason name                 |


## Examples
```yaml
Skills:
- message{m="<green>Healed <skill.var.event-amount>"} @trigger ~onHeal
```
