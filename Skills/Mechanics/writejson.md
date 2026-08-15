## Description
Writes a value into a JSON file. With `path=` (a dotted key path), sets that one value —
creating intermediate objects as needed — without touching the rest of the file; without
`path=`, `value=` is parsed as a whole JSON document and replaces the entire file.

Files may be located at any path the script provides — there is no sandboxing to the plugin's
data folder. Writes update the in-memory cache immediately and persist to disk asynchronously.


## Attributes
| Attribute | Aliases | Description                                                | Default |
|-----------|---------|----------------------------------------------------------------|---------|
| file      |         | Path to the JSON file                                            | none (required) |
| path      |         | Dotted key path within the file to write. Omit to write the whole file | (whole file) |
| value     |         | The string value to write (single-path mode) or a full JSON document (whole-file mode) | none (required) |


## Examples
```yaml
WriteJsonValue:
  Skills:
  - writejson{file=data.json;path=options.Settings.example;value=true} @trigger
```

```yaml
WriteWholeJsonFile:
  Skills:
  - 'writejson{file=data.json;value={"a":1,"b":"two"}} @trigger'
```
> Note the whole line is single-quoted — the JSON value itself contains characters (`{`, `}`,
> `:`) that would otherwise confuse YAML/skill-line parsing if left unquoted.


## Aliases
None.


## See Also
- [readjson](Skills-Mechanics-readjson) — read a JSON file.
- [removejsonkey](Skills-Mechanics-removejsonkey) — delete a key from a JSON file.
- [writeyaml](Skills-Mechanics-writeyaml) — the YAML equivalent.
