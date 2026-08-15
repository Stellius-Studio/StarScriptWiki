## Description
Fires once, shortly after the server starts up and all scripts finish their initial load. This
is not a Bukkit event — it's driven by StarScript's own scheduler — and it has no real player
caster; it uses a virtual caster anchored at the first world's spawn location.


## Config
| Attribute | Description                                                                    | Default |
|-----------|---------------------------------------------------------------------------------------|---------|
| delay     | Ticks to wait after the initial script load completes before firing (minimum enforced 1) | 1       |


## Skill Variables
None.


## Examples
```yaml
Skills:
- log{m="StarScript is ready — initializing global state."} @onlineplayers ~onServerStart{delay=20}
```


## See Also
- [timer](Skills-Triggers-timer) — the other scheduled (non-Bukkit-event) trigger, for repeating fires.
