## Description
Fires when a player takes damage caused by a block (`EntityDamageByBlockEvent`), e.g. cactus,
falling anvils, or lava.


## Config
| Attribute | Description                                    | Default |
|-----------|-----------------------------------------------------|---------|
| block     | Only fire if the damaging block's type matches        | any     |


## Skill Variables
| Variable       | Description                                              |
|----------------|----------------------------------------------------------|
| `event-cause`    | The `EntityDamageEvent.DamageCause` name                |
| `event-damage`   | The raw damage amount                                    |
| `event-block`    | The damaging block's type name (only if a block is known) |


## Examples
```yaml
Skills:
- message{m="<red>Ouch, that cactus hurt!"} @trigger ~onDamageByBlock{block=CACTUS}
```
