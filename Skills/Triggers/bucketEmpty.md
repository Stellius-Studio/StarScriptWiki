## Description
Fires when a player empties a bucket into the world (`PlayerBucketEmptyEvent`).


## Config
| Attribute | Description                       | Default |
|-----------|----------------------------------------|---------|
| block     | Material filter on the block clicked        | any     |


## Skill Variables
| Variable      | Description               |
|-----------------|---------------------------------|
| `event-block`    | The clicked block's material name |


## Examples
```yaml
Skills:
- message{m="<aqua>You placed a fluid on <skill.var.event-block>."} @trigger ~onBucketEmpty
```


## See Also
- [bucketFill](Skills-Triggers-bucketFill) — the filling equivalent.
