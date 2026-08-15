## Description
Reads one of MythicEnchants' numeric anvil/grindstone config values into a skill variable.

Valid `key=` values:
- `anvilcostmultiplier` — the anvil XP-cost multiplier (decimal)
- `grindstonexpreturnpercent` — the percentage of XP returned by the grindstone (integer)


## Attributes
| Attribute | Aliases | Description                                                    | Default |
|-----------|---------|--------------------------------------------------------------------|---------|
| key       |         | Which config value to read — `anvilcostmultiplier` or `grindstonexpreturnpercent` | none (required) |
| var       |         | The skill variable name to store the value into                    | the `key` value |


## Examples
```yaml
Skills:
- getmenchanvilconfig{key=anvilcostmultiplier;var=costMult} @trigger
```

```yaml
Skills:
- getmenchanvilconfig{key=grindstonexpreturnpercent} @trigger
- message{m="Grindstone returns <skill.var.grindstonexpreturnpercent>% XP"} @trigger
```


## Aliases
None.
