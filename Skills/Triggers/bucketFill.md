## Description
Fires when a player fills a bucket from the world (`PlayerBucketFillEvent`).


## Config
| Attribute | Description                                    | Default |
|-----------|-----------------------------------------------------|---------|
| block     | Material filter on the block that was filled from        | any     |


## Skill Variables
| Variable      | Description               |
|-----------------|---------------------------------|
| `event-block`    | The source block's material name  |


## Examples
```yaml
Skills:
- message{m="<aqua>Bucket filled from <skill.var.event-block>."} @trigger ~onBucketFill{block=WATER}
```


## See Also
- [bucketEmpty](Skills-Triggers-bucketEmpty) — the emptying equivalent.
