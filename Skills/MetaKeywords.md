## Introduction
MythicMobs has a built-in **chained value-transform system** called MetaKeywords: any
placeholder can have extra `.keyword` segments appended after it to transform its value —
uppercase a string, sort a list, add to a number, extract a vector component, and so on. This
works on StarScript's own placeholders (`<script.storage.KEY>`, `<script.storagelist.KEY>`)
exactly the same way it works on any of MythicMobs' native placeholders (`<caster.hp>`,
`<trigger.name>`, etc.) — it's not a StarScript feature, it's a MythicMobs capability
StarScript's own placeholders automatically inherit.

This page documents it because it isn't written up anywhere in StarScript's own docs, and is
easy to miss — a large amount of what looks like "we'd need a new mechanic/placeholder for that"
(string manipulation, list sorting, basic math) is often already possible today by chaining a
keyword onto an existing placeholder.


## Syntax
```
<placeholder.keyword>
<placeholder.keyword{arg=value;arg2=value2}>
<placeholder.keyword{arg=value}.keyword2{arg=value}>
```

Keywords chain: each keyword's output becomes the input to the next keyword in the chain, so
`<value.uppercase.trim>` runs `uppercase` then `trim` on the result. Arguments use the same
`{key=value;key2=value2}` syntax as mechanic/condition config — **not** positional dots
(`<value.substring.2.5>` is NOT valid; it's `<value.substring{from=2;to=5}>`).

Which keywords are available depends on the **declared type** of the placeholder being chained
from — a String-typed placeholder only accepts String keywords, a List-typed one only accepts
List keywords, and so on. This is a real constraint, not just a naming convention: MythicMobs
looks up keywords in a registry keyed by the placeholder's declared output type, not by
inspecting the actual runtime value. See [Placeholders](Skills-Placeholders) for which of StarScript's own
placeholders are String-typed vs. List-typed.


## String keywords
Input: any String-typed placeholder (e.g. `<script.storage.KEY>`, `<caster.name>`).

| Keyword | Args | Description |
|---|---|---|
| `uppercase` | none | Converts to uppercase |
| `lowercase` | none | Converts to lowercase |
| `capitalize` | none | Uppercases only the first character |
| `trim` | none | Trims leading/trailing whitespace |
| `size` | none | String length (returns a number) |
| `substring` | `from=`, `to=` | Substring from index `from` to `to` |
| `shift` | `amount=` | Drops the first `amount` characters |
| `split` | `regex=`, `with=` (default `,`) | Splits on `regex` then rejoins with `with` — a re-delimit, still returns a String, not a list |
| `replace` | `from=`, `to=` | Literal (non-regex) replace |
| `remove` | `value=` | Removes all literal occurrences of `value` |
| `insert` | `index=`, `value=` | Inserts `value` at character `index` |
| `append` | `value=` | Appends to the end |
| `prepend` | `value=` | Prepends to the start |
| `contains` | `value=` | Returns `true`/`false` |
| `startswith` | `value=` | Returns `true`/`false` |
| `endswith` | `value=` | Returns `true`/`false` |
| `indexOf` | `value=` | Index of first occurrence (number) |
| `lastIndexOf` | `value=` | Index of last occurrence (number) |
| `regex` | `regex=` | Returns `true`/`false` if the regex finds a match anywhere in the string |

There is no String `.reverse` keyword — only List has one.


## List keywords
Input: any List-typed placeholder (e.g. `<script.storagelist.KEY>`). **Lists are comma-separated
strings** — `<script.storagelist.KEY>` splits the underlying stored value on `,`, matching
MythicMobs' own native list serialization convention exactly (so a value written via
[setstorage](Skills-Mechanics-setstorage) as `a,b,c` already round-trips correctly here with no extra escaping needed).

| Keyword | Args | Description |
|---|---|---|
| `size` | none | Number of elements |
| `first` | none | First element |
| `last` | none | Last element |
| `get` | `index=` | Element at `index` |
| `indexOf` | `value=` | Index of first matching element (number) |
| `lastIndexOf` | `value=` | Index of last matching element (number) |
| `contains` | `value=` | Returns `true`/`false` |
| `join` | `with=` (default `,`) | Joins into a single String with `with` as the separator |
| `sort` | none | Natural lexicographic sort |
| `sortNum` | none | Sorts by parsing each element as a number |
| `shuffle` | none | Randomly shuffles |
| `reverse` | none | Reverses order |
| `trim` | none | Trims whitespace from each element |
| `slice` | `from=`, `to=` | Sublist from `from` to `to` |
| `sliceFrom` | `from=` | Sublist from `from` to the end |
| `sliceTo` | `to=` | Sublist from the start to `to` |
| `insert` | `index=`, `value=` | Inserts `value` at position `index` |
| `append` | `value=` | Adds `value` to the end |
| `prepend` | `value=` | Adds `value` to the start |
| `remove` | `index=` | Removes the element **at this index** — not value-based removal |
| `minNumber` | none | Minimum element, parsed as a number |
| `maxNumber` | none | Maximum element, parsed as a number |

With no chained keyword at all, a List-typed placeholder still displays correctly — it's
automatically formatted as a `", "`-joined string (e.g. `<script.storagelist.fruits>` shows
`apple, banana, cherry`), not a raw Java object.


## Math keywords
Input: any number-typed placeholder (e.g. `<caster.hp>`). Available on Double/Float/Integer/Long
placeholders alike, with type-appropriate arithmetic:

| Keyword | Args | Description |
|---|---|---|
| `abs` | none | Absolute value |
| `add` | `amount=` | Adds `amount` |
| `sub` | `amount=` | Subtracts `amount` |
| `mul` | `amount=` | Multiplies by `amount` |
| `div` | `amount=` | Divides by `amount` |
| `precision` | `amount=` | Rounds to `amount` decimal places (Double/Float only) |
| `round` | none | Rounds to a whole number (Double/Float only — note: rounding a Double returns a Long, rounding a Float returns an Integer, which affects what you can chain next) |

Example: `<caster.hp.add{amount=10}.mul{amount=2}>` — add 10 to the caster's health, then double
the result.


## Vector keywords
Input: any Vector-typed placeholder. Vectors are `x,y,z` comma-separated strings.

| Keyword | Args | Description |
|---|---|---|
| `add` | `amount=` (a `"x,y,z"` string) | Vector addition |
| `sub` | `amount=` | Vector subtraction |
| `mul` | `amount=` | Component-wise multiplication |
| `div` | `amount=` | Component-wise division |
| `length` | none | Vector magnitude (number) |
| `normalized` | none | Unit vector in the same direction |
| `rotate` | `axis=` (a `"x,y,z"` string), `angle=` | Rotates around an axis by `angle` |
| `x` / `y` / `z` | none | Individual component (number) |


## Location keywords
Input: any Location-typed placeholder.

| Keyword | Args | Description |
|---|---|---|
| `x` / `y` / `z` | none | Individual coordinate (number) |
| `yaw` / `pitch` | none | Individual rotation component (number) |
| `world` | none | World name (String) |
| `coords` | none | `x,y,z` as a List — chain further List keywords onto it, e.g. `.coords.get{index=1}` for Y |


## Boolean keywords
Input: any Boolean-typed placeholder.

| Keyword | Args | Description |
|---|---|---|
| `inverse` | none | Logical NOT |
| `union` | `with=` | Logical OR |
| `intersection` | `with=` | Logical AND |
| `difference` | `with=` | `value AND NOT with` |
| `number` | none | `1` or `0` |
| `yesno` | none | `"yes"` or `"no"` |


## See Also
- [Placeholders](Skills-Placeholders) — StarScript's own placeholders, including which are String-typed
  (`script.storage.KEY`) vs. List-typed (`script.storagelist.KEY`).
- [setstorage](Skills-Mechanics-setstorage) / [getstorage](Skills-Mechanics-getstorage) — write/read the values these keywords operate on.
