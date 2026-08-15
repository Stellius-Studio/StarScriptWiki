## Introduction
StarScript registers its own placeholders under the `script.` prefix, usable anywhere MythicMobs
placeholders are usable (skill lines, `Conditions:`, other plugin configs) — e.g. `<script.count>`.
The same values are also exposed to PlaceholderAPI as `%starscript_<key>%`, for use in other
plugins that only support PAPI placeholders (scoreboards, chat formatting plugins, etc).


## `script.<key>`
Any key defined under a script's `Placeholders:` YAML section becomes available as
`<script.KEY>`. The value is a template string, itself resolved against the viewing
player/context at read time (so it can nest other placeholders).

```yaml
MyScript:
  Placeholders:
    rank.display: "<gold><skill.var.rank></gold>"
```
```
<script.rank.display>
```


## `script.count`
The number of currently-loaded StarScript scripts.

```
<script.count>
```


## `script.storage.KEY`
Reads a live value from persistent key-value storage (see [setstorage](Skills-Mechanics-setstorage)/[getstorage](Skills-Mechanics-getstorage)) —
resolved fresh every time the placeholder is read, unlike `script.<key>` which is a fixed
per-script template.

Resolves per-viewer: if the placeholder is being resolved for a real online player, it reads
that player's personal storage; otherwise it falls back to global/shared storage.

```
<script.storage.coins>
```

This placeholder is **String-typed** — chaining a [MetaKeyword](Skills-MetaKeywords) onto it only
gives you String keywords (`.uppercase`, `.substring{from=;to=}`, `.contains{value=}`, etc.), even
if the stored value happens to look like a comma-separated list. For list operations, use
`script.storagelist.KEY` instead.


## `script.ext.NAME` (Premium)
A live value from a user-defined [Extension Scripting](Skills-extensions) placeholder (written
in Java or JavaScript) — resolved by calling that extension's handler fresh every time, just like
`script.storage.KEY`.

```yaml
# In an extension's Java/JS:
# @ScriptedExtension(name = "serverTps", type = ExtensionType.PLACEHOLDER)
# registerPlaceholder("serverTps", ctx => ...)
```
```
<script.ext.serverTps>
```

On Free builds this always resolves to MythicMobs' undefined-value sentinel, since extensions
(including their placeholders) don't register at all outside Premium.


## `script.storagelist.KEY`
Same live storage read as `script.storage.KEY`, but declared as a **List** — splitting the stored
value on `,` (matching MythicMobs' own native list format exactly, so anything already written
via [setstorage](Skills-Mechanics-setstorage) as `a,b,c` works here with no extra escaping).
This makes MythicMobs' List [MetaKeywords](Skills-MetaKeywords) (`.sort`, `.get{index=}`, `.join`,
`.shuffle`, `.first`, `.last`, etc.) available.

```
<script.storagelist.fruits>              → apple, banana, cherry   (auto ", "-joined display)
<script.storagelist.fruits.sort>         → apple, banana, cherry   (sorted)
<script.storagelist.fruits.get{index=0}> → apple
```


## PlaceholderAPI equivalents
Requires PlaceholderAPI to be installed. All `script.` placeholders above are mirrored under the
`starscript` PAPI identifier, with dots replaced by underscores (PAPI's own separator
convention):

| StarScript placeholder     | PlaceholderAPI equivalent           |
|-------------------------------|---------------------------------------|
| `<script.KEY>`                  | `%starscript_KEY%` (dots → underscores) |
| `<script.count>`                | `%starscript_count%`                  |
| `<script.storage.KEY>`          | `%starscript_storage_KEY%`            |
| `<script.ext.NAME>`             | `%starscript_ext_NAME%`               |

```
/papi parse <player> %starscript_storage_coins%
/papi parse <player> %starscript_ext_serverTps%
```


## See Also
- [setstorage](Skills-Mechanics-setstorage) / [getstorage](Skills-Mechanics-getstorage) — write/read the values `script.storage.*`/`script.storagelist.*` expose.
- [MetaKeywords](Skills-MetaKeywords) — the chained value-transform system (`.uppercase`, `.sort`, `.add{amount=}`, etc.) usable on these placeholders.
- [Scripts](Skills-Scripts) — the `Placeholders:` YAML section that backs `script.<key>`.
- [Extension Scripting](Skills-extensions) — write your own placeholder in Java/JS, backing `script.ext.NAME` (Premium).
