## Description
True if `value=` starts with `text=`.

Both `value=` and `text=` support placeholders, resolved fresh on every check.


## Attributes
| Attribute  | Aliases | Description                        | Default |
|------------|---------|-----------------------------------------|---------|
| value      |         | The string to test                        | (empty) |
| text       |         | The prefix to look for                    | (empty) |
| ignorecase |         | If `true`, comparison is case-insensitive | true    |


## Examples
```yaml
Skills:
- message{m="matches"} ?startswith{value=<skill.var.itemid>;text=item-} @trigger
```


## Aliases
None.


## See Also
- [endswith](Skills-Conditions-endswith) — suffix matching.
- [stringcontains](Skills-Conditions-stringcontains) — substring matching.
