## Description
True if ANY element of `list=` (a CSV-style string split by `separator=`) matches `value=` under
`operator=`.

`list=` and `value=` support placeholders (e.g. a `<skill.var.x>` populated via
[getstorage](Skills-Mechanics-getstorage)/[setstorage](Skills-Mechanics-setstorage)).


## Attributes
| Attribute  | Aliases | Description                                                              | Default |
|------------|---------|---------------------------------------------------------------------------|---------|
| list       |         | The CSV-style string to split and check                                    | (empty) |
| separator  |         | The delimiter to split `list=` on                                          | `,`     |
| operator   |         | `equals`, `contains`, `startswith`, `endswith`, `matches` (regex), `>`, `>=`, `<`, `<=` (numeric operators fall back to lexical comparison for non-numeric elements) | equals  |
| value      |         | The value to compare each element against                                  | (empty) |
| ignorecase |         | If `true`, string comparisons are case-insensitive (ignored by numeric operators) | true    |


## Examples
```yaml
Skills:
- message{m="found a match"} ?listany{list=apple,banana,cherry;operator=equals;value=banana} @trigger
```


## Aliases
None.


## See Also
- [listall](Skills-Conditions-listall) — requires every element to match.
