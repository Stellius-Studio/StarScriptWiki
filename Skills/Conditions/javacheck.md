## Description
Evaluates a static Java method or field via reflection and compares it against an expected value.
Part of StarScript's [Extension Scripting](Skills-extensions) reflection layer — **Premium
only**.


## Attributes
| Attribute | Aliases | Description                                                  | Default    |
|-----------|---------|-----------------------------------------------------------------|------------|
| class     |         | Fully-qualified (or `Imports:`-aliased) class name               | *required* |
| method    |         | Static method to call (mutually exclusive with `field=`)         | none       |
| field     |         | Static field to read (mutually exclusive with `method=`)          | none       |
| args      |         | Comma-separated arguments for `method=` (same syntax as [javanew](Skills-Mechanics-javanew)) | none |
| expect    |         | Literal to compare the result against                           | `true`     |

Exactly one of `method=`/`field=` should be given.


## Examples
```yaml
SkipOnHardcore:
  Conditions:
  - javacheck{class=org.bukkit.Bukkit;method=isHardcore;expect=false}
```
> Passes only when the server is not running in hardcore mode.


## Aliases
None.
