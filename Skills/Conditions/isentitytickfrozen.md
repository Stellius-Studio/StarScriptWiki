## Description
True if the caster is currently frozen by the server's tick manager (requires the server
itself to be frozen, the entity to not be a player, and the entity to have no player
passengers).


## Attributes
None.


## Examples
```yaml
Skills:
- message{m="This entity isn't ticking."} ?isentitytickfrozen @trigger
```


## Aliases
None.
