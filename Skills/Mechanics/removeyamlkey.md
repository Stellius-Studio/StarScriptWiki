## Description
Deletes one dotted key path from a YAML file, leaving the rest of the document intact.


## Attributes
| Attribute | Aliases | Description                    | Default |
|-----------|---------|-----------------------------------|---------|
| file      |         | Path to the YAML file               | none (required) |
| path      |         | Dotted key path to delete           | none (required) |


## Examples
```yaml
RemoveYamlKey:
  Skills:
  - removeyamlkey{file=data.yml;path=options.Settings.example} @trigger
```


## Aliases
None.


## See Also
- [writeyaml](Skills-Mechanics-writeyaml) — write a YAML file.
- [removejsonkey](Skills-Mechanics-removejsonkey) — the JSON equivalent.
