## Description
Writes a comma-separated list of MythicEnchants enchantment ids into a skill variable. The
`source=` field selects which underlying API lookup is used, and determines which other fields
are relevant:

- `source=all` (default) — every registered enchantment definition. No extra fields needed.
- `source=applicable` — every enchantment applicable to the caster's/target's `slot=` item.
  Uses `slot=`.
- `source=tag` — every enchantment carrying the given `tag=`. Requires `tag=`.
- `source=refs` — resolves a `;`-delimited `refs=` list of item-ref/enchant tokens. Requires `refs=`.
- `source=reagent` — every enchantment declaring the given `reagent=` key. Requires `reagent=`.


## Attributes
| Attribute | Aliases | Description                                                                     | Default |
|-----------|---------|------------------------------------------------------------------------------------|---------|
| source    |         | Which list to build — `all`, `applicable`, `tag`, `refs`, or `reagent`             | all |
| tag       |         | The tag to filter by (`source=tag` only)                                           | none |
| refs      |         | `;`-delimited list of refs to resolve (`source=refs` only)                         | none |
| reagent   |         | The reagent key to filter by (`source=reagent` only)                               | none |
| slot      |         | Which equipment slot's item to read — `hand`, `offhand`, `head`, `chest`, `legs`, `feet` (`source=applicable` only) | hand |
| var       |         | The skill variable name to store the comma-separated list into                     | enchantlist |


## Examples
```yaml
Skills:
- getmenchenchantlist{source=all;var=allEnchants} @trigger
```

```yaml
Skills:
- getmenchenchantlist{source=applicable;slot=hand;var=heldApplicable} @trigger
```

```yaml
Skills:
- getmenchenchantlist{source=tag;tag=curse;var=curseList} @trigger
```


## Aliases
None.
