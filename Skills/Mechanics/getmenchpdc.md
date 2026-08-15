## Description
Reads a plugin-namespaced PDC value from the caster's or targeted entity's item into a skill
variable.


## Attributes
| Attribute | Aliases | Description                                                                     | Default |
|-----------|---------|------------------------------------------------------------------------------------|---------|
| key       |         | The PDC key to read                                                                | none (required) |
| type      |         | The value's type — `string`, `int`, `double`, or `boolean`                         | string |
| slot      |         | Which equipment slot's item to read — `hand`, `offhand`, `head`, `chest`, `legs`, `feet` | hand |
| var       |         | The skill variable name to store the value into                                    | the `key` value |


## Examples
```yaml
Skills:
- getmenchpdc{key=owner;var=ownerName} @trigger
- message{m="Owner: <skill.var.ownerName>"} @trigger
```

```yaml
Skills:
- getmenchpdc{key=charges;type=int;slot=offhand} @trigger
```


## Aliases
None.
