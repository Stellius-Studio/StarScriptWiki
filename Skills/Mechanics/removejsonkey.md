## Description
Deletes one dotted key path from a JSON file, leaving the rest of the document intact.


## Attributes
| Attribute | Aliases | Description                    | Default |
|-----------|---------|-----------------------------------|---------|
| file      |         | Path to the JSON file               | none (required) |
| path      |         | Dotted key path to delete           | none (required) |


## Examples
```yaml
RemoveJsonKey:
  Skills:
  - removejsonkey{file=data.json;path=options.Settings.example} @trigger
```


## Aliases
None.


## See Also
- [writejson](Skills-Mechanics-writejson) — write a JSON file.
- [removeyamlkey](Skills-Mechanics-removeyamlkey) — the YAML equivalent.
