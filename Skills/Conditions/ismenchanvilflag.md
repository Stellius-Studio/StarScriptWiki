## Description
Checks one of MythicEnchants' anvil/grindstone boolean config flags. One condition covers every
flag rather than a separate condition per flag.

Valid `key=` values:
- `anvilcombining` — whether combining two enchanted items at an anvil is allowed
- `anvilsupporteditems` — whether the anvil enforces MythicEnchants' supported-item restrictions
- `anvilbypasstooexpensive` — whether the vanilla "Too Expensive!" cap is bypassed
- `anvilshowcostwhenunaffordable` — whether the anvil still shows its XP cost when unaffordable
- `freeanvil` — whether anvil use costs no XP/levels
- `grindstoneremoval` — whether the grindstone can remove MythicEnchants enchantments
- `grindstonekeepcurses` — whether the grindstone keeps cursed enchantments instead of stripping them


## Attributes
| Attribute | Aliases | Description                                        | Default |
|-----------|---------|---------------------------------------------------------|---------|
| key       |         | Which anvil/grindstone config flag to check (see list above) | none (required) |


## Examples
```yaml
Skills:
- message{m="Anvil combining is disabled here."} ?ismenchanvilflag{key=anvilcombining;NOT} @trigger
```

```yaml
Skills:
- message{m="The grindstone keeps curses on this server."} ?ismenchanvilflag{key=grindstonekeepcurses} @trigger
```


## Aliases
None.
