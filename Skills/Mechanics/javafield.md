## Description
Reads or writes a Java field via reflection. Part of StarScript's
[Extension Scripting](Skills-extensions) reflection layer — **Premium only**.


## Attributes
| Attribute | Aliases | Description                                                                    | Default    |
|-----------|---------|---------------------------------------------------------------------------------|------------|
| class     |         | Fully-qualified (or `Imports:`-aliased) class name — reads/writes a **static** field | none  |
| target    |         | `caster`, `target`, `origin`, or `var.NAME` — reads/writes an **instance** field on it | none |
| field     |         | Field name                                                                       | *required* |
| var       |         | Read mode — skill variable to store the field's value in                        | none       |
| value     |         | Write mode — value to set the field to (same syntax as [javanew](Skills-Mechanics-javanew)'s args) | none |

Exactly one of `class=`/`target=`, and exactly one of `var=`/`value=`, should be given.


## Examples
```yaml
ReadMaxInt:
  Skills:
  - javafield{class=java.lang.Integer;field=MAX_VALUE;var=max} ~onJoin
```
> Reads the static field `Integer.MAX_VALUE` into the `max` skill variable.


## Aliases
None.
