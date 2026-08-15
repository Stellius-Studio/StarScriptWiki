## Description
Constructs a Java object via reflection and stores it in a skill variable. Part of StarScript's
[Extension Scripting](Skills-extensions) reflection layer — **Premium only**.


## Attributes
| Attribute | Aliases | Description                                                        | Default    |
|-----------|---------|---------------------------------------------------------------------|------------|
| class     |         | Fully-qualified (or `Imports:`-aliased) class name to construct     | *required* |
| args      |         | Comma-separated constructor arguments (see below)                   | none       |
| var       |         | Skill variable to store the constructed object in                   | *required* |


## Argument syntax
Each `args=` entry is optionally prefixed `str:`/`int:`/`long:`/`double:`/`float:`/`bool:`, or
`null` for a real null argument; unprefixed values are guessed as int, then double, then boolean,
then left as a string. Escape a literal comma with `\,`. Overload resolution picks the most
specific constructor that matches the resolved argument types.


## Examples
```yaml
RollDice:
  Imports:
  - java.util.Random

  Skills:
  - javanew{class=Random;var=rng} ~onJoin
  - javainvoke{target=var.rng;method=nextInt;args=int:100;var=roll} ~onJoin
```
> Constructs a `java.util.Random` and stores it in the `rng` skill variable, then rolls a number
> from it with [javainvoke](Skills-Mechanics-javainvoke).


## Aliases
None.
