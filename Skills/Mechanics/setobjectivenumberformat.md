## Description
Sets how an objective's scores are displayed on the scoreboard.


## Attributes
| Attribute  | Aliases | Description                                                                 | Default |
|------------|---------|---------------------------------------------------------------------------------|---------|
| objective  |         | The objective's id                                                                | none (required) |
| format     |         | `blank` (hide numbers), `fixed` (literal text), or `styled` (styled number)       | fixed   |
| value      |         | Required for `fixed`/`styled` — literal text for `fixed`, MiniMessage style for `styled` | none |


## Examples
```yaml
Skills:
- setobjectivenumberformat{objective=kills;format=fixed;value=" kills"}
```

```yaml
Skills:
- setobjectivenumberformat{objective=kills;format=blank}
```


## Aliases
None.
