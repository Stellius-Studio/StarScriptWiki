## Description
Sets the modern (1.21.4+) list-based custom model data component, distinct from the legacy
single-integer value the `hascustommodeldata` condition checks.


## Attributes
| Attribute | Aliases | Description                                                              | Default |
|-----------|---------|----------------------------------------------------------------------------------|---------|
| slot      |         | Which equipment slot to affect: `hand` (default), `offhand`, `head`, `chest`, `legs`, `feet` | hand    |
| floats    |         | CSV of float values                                                              | none    |
| flags     |         | CSV of booleans                                                                   | none    |
| strings   |         | CSV of strings                                                                    | none    |
| colors    |         | CSV of hex colors (`RRGGBB`)                                                      | none    |


## Examples
```yaml
TagCustomVariant:
  Skills:
  - custommodeldatacomponent{floats="1.0,2.5";flags="true,false";strings="rare,glowing";colors="FF0000,00FF00"} @self
```


## Aliases
None.
