## Description
Writes a value into a YAML file. With `path=` (a dotted key path), sets that one value —
creating intermediate sections as needed — without touching the rest of the file; without
`path=`, `value=` is parsed as a whole YAML document and replaces the entire file.

In single-path mode, the raw string is automatically coerced to a boolean or number when it
unambiguously parses as one, so `value=true`/`value=5` round-trip as real YAML booleans/numbers
rather than quoted strings.

Files may be located at any path the script provides — there is no sandboxing to the plugin's
data folder. Writes update the in-memory cache immediately and persist to disk asynchronously.


## Attributes
| Attribute | Aliases | Description                                                | Default |
|-----------|---------|----------------------------------------------------------------|---------|
| file      |         | Path to the YAML file                                            | none (required) |
| path      |         | Dotted key path within the file to write. Omit to write the whole file | (whole file) |
| value     |         | The value to write (single-path mode, coerced to bool/number where possible) or a full YAML document (whole-file mode) | none (required) |


## Examples
```yaml
WriteYamlValue:
  Skills:
  - writeyaml{file=data.yml;path=options.Settings.example;value=true} @trigger
```

```yaml
WriteWholeYamlFile:
  Skills:
  - 'writeyaml{file=data.yml;value=a: 1\nb: two} @trigger'
```


## Aliases
None.


## See Also
- [readyaml](Skills-Mechanics-readyaml) — read a YAML file.
- [removeyamlkey](Skills-Mechanics-removeyamlkey) — delete a key from a YAML file.
- [writejson](Skills-Mechanics-writejson) — the JSON equivalent.
