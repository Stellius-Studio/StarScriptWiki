## Description
Loads a 64x64 PNG file from disk and applies it as the server-list favicon for all future
server-list pings.


## Attributes
| Attribute | Aliases | Description                              | Default |
|-----------|---------|--------------------------------------------|---------|
| path      |         | Path to the 64x64 PNG file to load           | none (required) |


## Examples
```yaml
SetServerIcon:
  Skills:
  - servericon{path=/plugins/StarScript/icon.png} @trigger
```


## Aliases
None.
