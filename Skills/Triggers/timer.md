## Description
Fires repeatedly on a fixed interval. This is not a Bukkit event — it's driven by StarScript's
own scheduler. By default it has no real player caster (a virtual caster anchored at the first
world's spawn location); with `perplayer=true` it fires once per currently-online player instead,
giving it a real player caster each time.


## Config
| Attribute | Description                                                                  | Default |
|-----------|-------------------------------------------------------------------------------------|---------|
| interval  | Ticks between each fire (20 ticks = 1 second). **Required** — the binding is silently skipped with a warning if missing or less than 1 | none    |
| perplayer | If true, fires once per currently-online player instead of once globally                | false   |


## Skill Variables
None.


## Examples
```yaml
Skills:
- broadcast{m="<gray>The server has been up for a while now."} @onlineplayers ~onTimer{interval=72000}
```

```yaml
# perplayer=true gives this a real player caster, firing once per online player every 5 seconds.
Skills:
- actionbar{m="<aqua><trigger.health>/<trigger.maxhealth> HP"} @trigger ~onTimer{interval=100;perplayer=true}
```


## See Also
- [serverStart](Skills-Triggers-serverStart) — the other scheduled (non-Bukkit-event) trigger, fires once.
