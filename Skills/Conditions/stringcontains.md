## Description
True if `value=` contains `text=` as a substring.

Both `value=` and `text=` support placeholders (e.g. `<skill.var.x>`, `<caster.name>`), resolved
fresh on every check.


## Attributes
| Attribute  | Aliases | Description                                    | Default |
|------------|---------|---------------------------------------------------|---------|
| value      |         | The string to search within                          | (empty) |
| text       |         | The substring to look for                             | (empty) |
| ignorecase |         | If `true`, comparison is case-insensitive             | true    |


## Examples
```yaml
Skills:
- message{m="admin detected"} ?stringcontains{value=<skill.var.username>;text=admin} @trigger
```


## Aliases
None.


## See Also
- [stringmatches](Skills-Conditions-stringmatches) — regex-based matching.
- [startswith](Skills-Conditions-startswith) / [endswith](Skills-Conditions-endswith) — prefix/suffix matching.
