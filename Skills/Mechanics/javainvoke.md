## Description
Calls a Java method via reflection, optionally storing the return value in a skill variable. Part
of StarScript's [Extension Scripting](Skills-extensions) reflection layer — **Premium only**.


## Attributes
| Attribute | Aliases | Description                                                                    | Default    |
|-----------|---------|---------------------------------------------------------------------------------|------------|
| class     |         | Fully-qualified (or `Imports:`-aliased) class name — calls a **static** method   | none       |
| target    |         | `caster`, `target`, `origin`, or `var.NAME` — calls an **instance** method on it | none       |
| method    |         | Method name to call                                                              | *required* |
| args      |         | Comma-separated method arguments (same syntax as [javanew](Skills-Mechanics-javanew)) | none |
| var       |         | Skill variable to store the return value in                                     | none       |

Exactly one of `class=`/`target=` should be given.


## Examples
```yaml
AnnounceJoin:
  Skills:
  - javainvoke{class=org.bukkit.Bukkit;method=broadcastMessage;args=str:<trigger.name> joined!} ~onJoin
```
> Calls the static `Bukkit.broadcastMessage(String)` method directly.

```yaml
ExtinguishOnDamage:
  Skills:
  - javainvoke{target=caster;method=setFireTicks;args=int:0} ~onDamaged
```
> Calls the instance method `caster.setFireTicks(0)` on the casting entity.


## Aliases
None.
