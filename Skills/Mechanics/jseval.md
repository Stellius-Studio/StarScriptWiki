## Description
Evaluates an inline JavaScript snippet (GraalJS) against the current cast. Part of StarScript's
[Extension Scripting](Skills-extensions) reflection layer — **Premium only**. Compiled once per
skill line at load time, then re-invoked on every cast.


## Attributes
| Attribute | Aliases | Description                                                     | Default    |
|-----------|---------|-------------------------------------------------------------------|------------|
| js        |         | The JavaScript snippet body, wrapped as `function(ctx) { ... }`    | *required* |

`ctx` inside the snippet is the same context object Java/JS extensions receive — `ctx.caster()`,
`ctx.targetEntity()`, `ctx.targetLocation()`, `ctx.origin()`, `ctx.config()`,
`ctx.resolve(template)`, `ctx.variable(name)`/`ctx.variable(name, value)`. See
[Extension Scripting](Skills-extensions) for the full JS API.


## Examples
```yaml
IgniteImmune:
  Skills:
  - 'jseval{js="ctx.caster().setFireTicks(0)"}' ~onDamaged
```
> Extinguishes the caster whenever they take damage.

The whole line must be wrapped in single quotes when `js=` contains a space, since it isn't a
simple unquoted value — see the [Scripts](Skills-Scripts) page's note on quoting `Skills:` lines.


## Aliases
None.
