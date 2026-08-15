## Description
True if ALL elements of `list=` (a CSV-style string split by `separator=`) match `value=` under
`operator=`. An empty list is always `false`.

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
- message{m="all scores passed"} ?listall{list=<skill.var.scores>;operator=>;value=50} @trigger
```


## Aliases
None.


## See Also
- [listany](Skills-Conditions-listany) — requires at least one element to match.
