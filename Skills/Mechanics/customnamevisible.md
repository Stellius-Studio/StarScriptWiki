## Description
Toggles whether an entity's custom name is always visible (rather than only when hovered over).


## Attributes
| Attribute | Aliases | Description                          | Default |
|-----------|---------|------------------------------------------|---------|
| state     |         | `true` to always show the custom name, `false` to only show it on hover | true    |


## Examples
```yaml
AlwaysShowName:
  Skills:
  - customnamevisible @self
```

```yaml
HideNameplate:
  Skills:
  - customnamevisible{state=false} @self
```


## Aliases
None.
