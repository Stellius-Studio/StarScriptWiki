## Description
Reads one of MythicEnchants' misc config/debug flags into a skill variable, as a string (booleans
become `"true"`/`"false"`).

Valid `key=` values:
- `debug` — whether debug logging is enabled
- `checkforupdates` — whether update-checking is enabled
- `language` — the configured language code
- `datapackenabled` — whether datapack generation is enabled
- `datapackautogenerate` — whether the datapack auto-regenerates
- `datapackname` — the configured datapack name
- `treasureallowedattable` — whether treasure-only enchants can appear at the custom table
- `vanillaintable` — whether vanilla enchantments can appear at the custom table
- `cleanupenabled` — whether orphan/stale-enchant cleanup is enabled
- `cleanupsilent` — whether cleanup runs without logging


## Attributes
| Attribute | Aliases | Description                                                    | Default |
|-----------|---------|--------------------------------------------------------------------|---------|
| key       |         | Which config/debug flag to read (see list above)                   | none (required) |
| var       |         | The skill variable name to store the value into                    | the `key` value |


## Examples
```yaml
Skills:
- getmenchconfig{key=debug;var=debugState} @trigger
```

```yaml
Skills:
- getmenchconfig{key=language} @trigger
- message{m="Language: <skill.var.language>"} @trigger
```


## Aliases
None.
