## Description
Toggles the server whitelist, optionally enforcing it immediately by kicking currently-online
non-whitelisted, non-operator players.


## Attributes
| Attribute | Aliases | Description                                                            | Default |
|-----------|---------|---------------------------------------------------------------------------|---------|
| state     |         | `true` to enable the whitelist, `false` to disable it                     | true    |
| kick      |         | If `true` (and `state=true`), immediately kicks online players who aren't whitelisted or op | false   |


## Examples
```yaml
LockServer:
  Skills:
  - whitelist{state=true;kick=true} @trigger
```
> Enables the whitelist and immediately kicks anyone online who isn't whitelisted or an operator.

```yaml
OpenServer:
  Skills:
  - whitelist{state=false} @trigger
```


## Aliases
None.
