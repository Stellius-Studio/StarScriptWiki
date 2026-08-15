## Description
Fires on fishing rod events (`PlayerFishEvent`) — casting, catching, or failing.


## Config
| Attribute | Description                                                                        | Default |
|-----------|---------------------------------------------------------------------------------------|---------|
| state     | Only fire if the fishing state matches (matches `PlayerFishEvent.State`, e.g. `CAUGHT_FISH`, `FISHING`, `IN_GROUND`, `FAILED_ATTEMPT`) | any     |


## Skill Variables
| Variable       | Description             |
|------------------|------------------------------|
| `event-state`     | The fishing state name        |


## Examples
```yaml
Skills:
- message{m="<aqua>You caught a fish!"} @trigger ~onFish{state=CAUGHT_FISH}
```
