## 1. Install
Requires [MythicMobs](https://www.mythiccraft.io/) (hard dependency — StarScript won't enable
without it). Drop `StarScript-<version>.jar` into `plugins/`, restart the server.

On first start, StarScript creates:
```
plugins/StarScript/
  config.yml
  scripts/
    example.yml
```
`scripts/example.yml` is a real, working example file — read it first, it doubles as inline
documentation for the trigger/condition/YAML-quoting rules below.


## 2. Your first script
Any `.yml` file under `plugins/StarScript/scripts/` (subfolders allowed) can hold any number of
scripts — each top-level YAML key is one script name. Create
`plugins/StarScript/scripts/hello.yml`:

```yaml
WelcomeScript:
  Skills:
  - message{m="<green>Welcome to the server, <trigger.name>!"} @trigger ~onJoin
```

Reload with `/ss reload` (or restart). Join the server — you'll see the message.

**What each part means:**
- `WelcomeScript` — the script's name. Also its registered MythicMobs skill name, so mobs/items
  can invoke it via `skill{s=WelcomeScript}`.
- `Skills:` — a list of skill lines, exactly like a MythicMobs mob's `Skills:` section. Every
  mechanic, condition, and targeter MythicMobs (and any installed addon) provides works here for
  free — StarScript only adds new ones for genuine gaps (see [Mechanics](Skills-Mechanics)/[Conditions](Skills-Conditions)).
- `message{m="..."}` — the mechanic. `<trigger.name>` is a normal MythicMobs placeholder (the
  player who triggered this line).
- `@trigger` — the targeter: who the mechanic acts on. `@trigger` means "whoever caused the
  event."
- `~onJoin` — the trigger: WHEN this line fires. See [Triggers](Skills-Triggers) for the full catalog, or use
  any MythicMobs-native trigger name directly (no wrapping needed).


## 3. Add a condition
```yaml
OreAlert:
  Cooldown: 5
  Skills:
  - message{m="<aqua>You mined <skill.var.event-block>!"} @trigger ~onBlockBreak{block=DIAMOND_ORE,DEEPSLATE_DIAMOND_ORE}
```
- `Cooldown: 5` — a per-player cooldown in seconds (parsed by MythicMobs, same as a mob's own
  `Cooldown:`).
- `~onBlockBreak{block=...}` — the trigger token's `{}` holds trigger-specific config; here it
  filters to only these two block types.
- `<skill.var.event-block>` — a skill variable. Many triggers expose contextual data this way
  (the broken block's material, in this case) — check each trigger's wiki page for what it
  exposes.

To gate a line on something else, use a condition:
```yaml
Skills:
- message{m="<gold>Nice diamond, VIP!"} ?hasscoreboardtag{tag=vip} @trigger ~onBlockBreak{block=DIAMOND_ORE}
```
`?condition{config}` goes between the mechanic and the targeter — see [Conditions](Skills-Conditions) for
StarScript's own additions on top of every built-in MythicMobs condition.


## 4. Store and reuse data
```yaml
GiveCoinsOnKill:
  Skills:
  - incrementstorage{key=coins;amount=10;var=coins} @trigger ~onKill
  - message{m="<gold>+10 coins! You now have <skill.var.coins>."} @trigger ~onKill
```
[setstorage](Skills-Mechanics-setstorage)/[getstorage](Skills-Mechanics-getstorage)/[incrementstorage](Skills-Mechanics-incrementstorage) persist per-player (or global) key-value data
across restarts. Read it back anywhere as a placeholder too: `<script.storage.coins>` (see
[Placeholders](Skills-Placeholders)).


## 5. A command that runs a script
```yaml
DailyReward:
  Commands:
  - name: daily
    permission: starscript.daily
    usage: "/daily"
  Skills:
  - incrementstorage{key=coins;amount=100;var=coins} @trigger
  - message{m="<gold>Claimed! Balance: <skill.var.coins>"} @trigger
```
Registers a real `/daily` command that runs this script's `Skills:` list when used — see
[Scripts](Skills-Scripts) for the full `Commands:`/`Placeholders:` schema.


## 6. Useful commands while you work
| Command | Effect |
|---|---|
| `/ss reload` | Reload every script file |
| `/ss list` | List all currently-loaded scripts |
| `/ss info <script>` | Show a script's bindings/details |
| `/ss test <script>` | Manually fire a script (for scripts with no natural trigger, or quick testing) |
| `/ss debug` | Toggle debug logging |


## Common pitfalls
- **Colons in text**: a `Skills:` line is plain YAML text, and YAML treats `: ` (colon-space) as
  a mapping separator — even inside quotes. If a line's text contains `: ` anywhere (e.g.
  `message{m="Rank: VIP"}`), wrap the **whole line** in single quotes:
  `- 'message{m="Rank: VIP"} @trigger'`. Skipping this silently drops the line — no crash, no
  visible error, just a missing trigger. If a script loads with fewer bindings than expected,
  check `/ss reload`'s console output for a warning about a line parsed as a YAML map instead of
  text.
- **Lines with no trigger token** run on every one of the script's events — handy shorthand when
  a whole script only has one trigger, easy to trip over when it has several.
- **Trigger config vs. mechanic config**: `~onBlockBreak{block=X}` filters WHEN the line fires;
  `message{m=X}` configures the mechanic itself — they're separate `{}` blocks on the same line
  and don't share keys.


## Where to go next
- [Scripts](Skills-Scripts) — full script-file schema (`Commands:`, `Placeholders:`, skill variables).
- [Triggers](Skills-Triggers) — the full trigger catalog.
- [Mechanics](Skills-Mechanics) — StarScript's custom mechanics.
- [Conditions](Skills-Conditions) — StarScript's custom conditions.
- [Placeholders](Skills-Placeholders) / [MetaKeywords](Skills-MetaKeywords) — placeholders and the chained value-transform system.
