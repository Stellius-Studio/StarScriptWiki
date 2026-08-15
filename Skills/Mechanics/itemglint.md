## Description
Forces an item to glow (or not glow) regardless of its actual enchantments, or clears the
override so its natural enchant-based glow applies again.


## Attributes
| Attribute | Aliases | Description                                                          | Default |
|-----------|---------|---------------------------------------------------------------------|---------|
| slot      |         | Which equipment slot to affect: `hand` (default), `offhand`, `head`, `chest`, `legs`, `feet` | hand    |
| state     |         | `true` forces glow, `false` forces no glow, `default`/`clear`/`null` clears the override | true    |


## Examples
```yaml
ForceGlow:
  Skills:
  - itemglint @self
```

```yaml
ForceNoGlow:
  Skills:
  - itemglint{state=false} @self
```

```yaml
ClearGlintOverride:
  Skills:
  - itemglint{state=default} @self
```


## Aliases
None.
