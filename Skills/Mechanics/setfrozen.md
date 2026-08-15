## Description
Freezes or unfreezes the server's tick loop — equivalent to vanilla's `/tick freeze`.


## Attributes
| Attribute | Aliases | Description                       | Default |
|-----------|---------|----------------------------------------|---------|
| state     |         | `true` freezes the server, `false` unfreezes it | true |


## Examples
```yaml
Skills:
- setfrozen
```

```yaml
Skills:
- setfrozen{state=false}
```


## Aliases
None.
