## Description
True if the given objective's scores can be modified by plugins/commands. Some criteria (like
vanilla stat-tracking ones) are read-only.


## Attributes
| Attribute  | Aliases | Description             | Default |
|------------|---------|------------------------------|---------|
| objective  |         | The objective's id to check    | none (required) |


## Examples
```yaml
Skills:
- setscore{objective=kills;value=1} ?isobjectivemodifiable{objective=kills} @trigger
```


## Aliases
None.
