## Description
True if `value=` ends with `text=`.

Both `value=` and `text=` support placeholders, resolved fresh on every check.


## Attributes
| Attribute  | Aliases | Description                        | Default |
|------------|---------|-----------------------------------------|---------|
| value      |         | The string to test                        | (empty) |
| text       |         | The suffix to look for                    | (empty) |
| ignorecase |         | If `true`, comparison is case-insensitive | true    |


## Examples
```yaml
Skills:
- message{m="matches"} ?endswith{value=<skill.var.filename>;text=.json} @trigger
```


## Aliases
None.


## See Also
- [startswith](Skills-Conditions-startswith) — prefix matching.
- [stringcontains](Skills-Conditions-stringcontains) — substring matching.
