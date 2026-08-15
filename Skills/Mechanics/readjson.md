## Description
Reads a JSON file into a skill variable. With `path=` (a dotted key path, e.g.
`options.Settings.example`), reads just that one value; without it, reads the entire file as
compact JSON text.

Files may be located at any path the script provides — there is no sandboxing to the plugin's
data folder. Reads are served from an in-memory cache after the first access.


## Attributes
| Attribute | Aliases | Description                                                | Default |
|-----------|---------|----------------------------------------------------------------|---------|
| file      |         | Path to the JSON file                                            | none (required) |
| path      |         | Dotted key path within the file to read. Omit to read the whole file | (whole file) |
| var       |         | The skill variable name to store the result in                   | none (required) |
| default   |         | Fallback value if the path/file doesn't resolve                   | (empty) |


## Examples
```yaml
ReadJsonValue:
  Skills:
  - readjson{file=data.json;path=options.Settings.example;var=example;default=missing} @trigger
  - message{m="<aqua>example -> <skill.var.example>"} @trigger
```

```yaml
ReadWholeJsonFile:
  Skills:
  - readjson{file=data.json;var=whole} @trigger
```


## Aliases
None.


## See Also
- [writejson](Skills-Mechanics-writejson) — write a JSON file.
- [removejsonkey](Skills-Mechanics-removejsonkey) — delete a key from a JSON file.
- [readyaml](Skills-Mechanics-readyaml) — the YAML equivalent.
