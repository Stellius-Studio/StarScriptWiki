What is StarScript?
-------------------

StarScript is "Skript for the Mythic ecosystem" — write server-side, event-driven scripts using
the exact same YAML syntax MythicMobs itself uses for mob configs. A StarScript script is a real
registered MythicMobs skill under the hood, so it gets every mechanic, condition, and targeter
MythicMobs (and any installed MythicMobs addon) provides — StarScript only adds new
mechanics/conditions/triggers for genuine gaps versus what Skript scripts can do that MythicMobs
alone couldn't.

As a brief summary, StarScript allows you to:

-   **Event-driven scripts**:
    React to a broad catalog of Bukkit/Paper events via `~onX{config}` trigger tokens, or react to
    any MythicMobs-native trigger directly, using the exact same `Skills:`/`Conditions:`/targeter
    syntax as a mob config.

<!-- -->

-   **Custom mechanics**:
    Ban/kick/pardon players, toggle the whitelist/PvP, load/save/resize worlds, control
    species-specific mob animation states (Panda, Goat, Allay, Warden), recolor/reglint items,
    control server-list visibility, and persist data (key-value storage, JSON, YAML files) —
    none of which MythicMobs has a built-in mechanic for.

<!-- -->

-   **Custom conditions**:
    Text-pattern matching (contains/regex/starts-with/ends-with), CSV-list boolean logic
    (any/all), and a broad set of entity/item/block/player state checks (mirroring Skript's own
    condition set) that MythicMobs' built-in conditions didn't cover.

<!-- -->

-   **Script-defined commands & placeholders**:
    Register real `/commands` that run a script's `Skills:`, and expose script-computed values as
    `<script.KEY>` placeholders (also mirrored to PlaceholderAPI).

Getting Started
-----

-   [Quickstart](Quickstart) — install StarScript and write your first script in 5 minutes.
-   [Scripts](Skills-Scripts) — how a script file is structured.
-   [Pack Scripts](Skills-PackScripts) — ship scripts/targeters/triggers/extensions inside a MythicMobs pack instead of StarScript's own data folder.
-   [Triggers](Skills-Triggers) — the full trigger catalog (`~onX` tokens).
-   [Compound Triggers](Skills-CompoundTriggers) — combine triggers into one named `~onName`, OR/AND-any-order.
-   [Mechanics](Skills-Mechanics) — StarScript's custom mechanics.
-   [Conditions](Skills-Conditions) — StarScript's custom conditions.
-   [Targeters](Skills-Targeters) — StarScript's custom targeters.
-   [Extension Scripting](Skills-extensions) — write your own mechanics/conditions/targeters in Java or JavaScript, or call Java directly from a script (Premium).
-   [Placeholders](Skills-Placeholders) — StarScript's placeholders.
-   [MetaKeywords](Skills-MetaKeywords) — chain `.uppercase`/`.sort`/`.add{amount=}`-style transforms onto any placeholder.
-   [Addon API](AddonAPI) — for plugin developers: register your own mechanics/conditions/targeters/triggers/placeholders into StarScript from another plugin.
