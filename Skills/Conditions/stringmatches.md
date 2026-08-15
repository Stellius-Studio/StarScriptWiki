## Description
True if `value=` matches the regular expression `pattern=` anywhere within it (i.e. "contains a
match," not a full-string match). An invalid regex makes the condition always false.

`value=` supports placeholders (e.g. `<skill.var.x>`), resolved fresh on every check. `pattern=`
is always a literal Java regex string.


## Attributes
| Attribute | Aliases | Description                            | Default |
|-----------|---------|--------------------------------------------|---------|
| value     |         | The string to test                            | (empty) |
| pattern   |         | The Java regular expression to match against | (empty) |


## Examples
```yaml
Skills:
- message{m="matches item id pattern"} ?stringmatches{value=<skill.var.itemid>;pattern=item-\d+} @trigger
```


## Aliases
- [x] regexmatches


## See Also
- [stringcontains](Skills-Conditions-stringcontains) — plain substring matching.
