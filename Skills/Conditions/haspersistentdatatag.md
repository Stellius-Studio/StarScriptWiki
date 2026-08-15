## Description
True if the caster's persistent data container has a tag with the given key name.

Matches by the un-namespaced part of the key, so this works against tags written by any plugin
(not just StarScript's own namespace).


## Attributes
| Attribute | Aliases | Description                            | Default |
|-----------|---------|---------------------------------------------|---------|
| key       |         | The (un-namespaced) persistent data key name   | (empty) |


## Examples
```yaml
Skills:
- message{m="has tag"} ?haspersistentdatatag{key=quest_complete} @trigger
```


## Aliases
None.
