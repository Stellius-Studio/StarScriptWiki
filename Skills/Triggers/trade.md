## Description
Fires when a player completes a trade with a villager/merchant (`PlayerTradeEvent`). The target
is the merchant.


## Config
None.


## Skill Variables
| Variable       | Description                          |
|------------------|-------------------------------------------|
| `event-result`     | The material name of the trade's result item |


## Examples
```yaml
Skills:
- message{m="<aqua>Traded for <skill.var.event-result>"} @trigger ~onTrade
```
