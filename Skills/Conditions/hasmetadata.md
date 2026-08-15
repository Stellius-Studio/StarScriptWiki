## Description
True if the caster has metadata set under the given key (via Bukkit's `Metadatable` API — often
set by other plugins).


## Attributes
| Attribute | Aliases | Description                | Default |
|-----------|---------|-------------------------------|---------|
| key       |         | The metadata key to check for   | (empty) |


## Examples
```yaml
Skills:
- message{m="has metadata"} ?hasmetadata{key=vanished} @trigger
```


## Aliases
None.
