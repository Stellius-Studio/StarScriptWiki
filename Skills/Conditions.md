## Introduction
StarScript scripts get every MythicMobs condition for free (including MM's generic
`CompareValues`, string-equals, and variable conditions). The conditions below are StarScript's
own additions, for gaps MythicMobs had no built-in equivalent for — mostly text-pattern matching,
CSV-list boolean logic, and a broad set of entity/item/block/player state checks Skript has that
MythicMobs didn't cover.

Used exactly like a built-in MythicMobs condition, via the inline `?condition{...}` syntax on a
skill line, or a `Conditions:`/`TargetConditions:`/`TriggerConditions:` block.


## Text & list
- [stringcontains](Skills-Conditions-stringcontains) — substring match.
- [stringmatches](Skills-Conditions-stringmatches) — regex match.
- [startswith](Skills-Conditions-startswith) / [endswith](Skills-Conditions-endswith) — prefix/suffix match.
- [listany](Skills-Conditions-listany) / [listall](Skills-Conditions-listall) — CSV-list boolean logic.
- [hasstorage](Skills-Conditions-hasstorage) — check persistent storage (presence or exact value) inline, without a separate getstorage step.


## Entity state
Allay/Camel/Ghast/Enderman/Wither/Panda/Goat/Horse/Axolotl/Strider-specific checks, plus generic
entity-state checks:

[candupe](Skills-Conditions-candupe), [iscameldashing](Skills-Conditions-iscameldashing), [canage](Skills-Conditions-canage), [canbreed](Skills-Conditions-canbreed), [candespawn](Skills-Conditions-candespawn),
[canpickupitems](Skills-Conditions-canpickupitems), [isenderstared](Skills-Conditions-isenderstared), [isentitywet](Skills-Conditions-isentitywet), [iswithercharged](Skills-Conditions-iswithercharged),
[iswitherskullcharged](Skills-Conditions-iswitherskullcharged), [isghastcharging](Skills-Conditions-isghastcharging), [iscustomnamevisible](Skills-Conditions-iscustomnamevisible), [isdancing](Skills-Conditions-isdancing),
[ishorseeating](Skills-Conditions-ishorseeating), [ishandraised](Skills-Conditions-ishandraised), [isinlove](Skills-Conditions-isinlove), [isjumping](Skills-Conditions-isjumping), [isleftHanded](Skills-Conditions-isleftHanded),
[ispathfinding](Skills-Conditions-ispathfinding), [ispersistent](Skills-Conditions-ispersistent), [isplayingdead](Skills-Conditions-isplayingdead), [isresponsive](Skills-Conditions-isresponsive), [isriptiding](Skills-Conditions-isriptiding),
[isscreaming](Skills-Conditions-isscreaming), [isshivering](Skills-Conditions-isshivering), [issilent](Skills-Conditions-issilent), [issleeping](Skills-Conditions-issleeping), [isswimming](Skills-Conditions-isswimming), [isticking](Skills-Conditions-isticking),
[isvalid](Skills-Conditions-isvalid), [isignited](Skills-Conditions-isignited), [ispandaeating](Skills-Conditions-ispandaeating), [ispandaonback](Skills-Conditions-ispandaonback), [ispandarolling](Skills-Conditions-ispandarolling),
[ispandascared](Skills-Conditions-ispandascared), [ispandasneezing](Skills-Conditions-ispandasneezing)


## Block / world / chunk state
[isbeehivesedated](Skills-Conditions-isbeehivesedated), [isbellresonating](Skills-Conditions-isbellresonating), [isbellringing](Skills-Conditions-isbellringing), [isentitystoragefull](Skills-Conditions-isentitystoragefull),
[ishangingsignglowing](Skills-Conditions-ishangingsignglowing), [ischunkloaded](Skills-Conditions-ischunkloaded), [ispassable](Skills-Conditions-ispassable), [islidopen](Skills-Conditions-islidopen), [ispvpenabled](Skills-Conditions-ispvpenabled),
[isredstonepowered](Skills-Conditions-isredstonepowered), [isslimechunk](Skills-Conditions-isslimechunk)


## Item / equippable-component state
[isitemunbreakable](Skills-Conditions-isitemunbreakable), [isequipdispensable](Skills-Conditions-isequipdispensable), [isequipswappable](Skills-Conditions-isequipswappable), [isequipdamageonhurt](Skills-Conditions-isequipdamageonhurt),
[isequiponinteract](Skills-Conditions-isequiponinteract), [hascustommodeldata](Skills-Conditions-hascustommodeldata), [hasenchantglintoverride](Skills-Conditions-hasenchantglintoverride),
[hasitemtooltip](Skills-Conditions-hasitemtooltip), [isitemfireresistant](Skills-Conditions-isitemfireresistant), [ispotioneffecthasicon](Skills-Conditions-ispotioneffecthasicon),
[ispotioneffecthasparticles](Skills-Conditions-ispotioneffecthasparticles), [ispotiontypeinstant](Skills-Conditions-ispotiontypeinstant), [haslootable](Skills-Conditions-haslootable), [willdespawn](Skills-Conditions-willdespawn),
[hascomponent](Skills-Conditions-hascomponent), [isdamageresistant](Skills-Conditions-isdamageresistant)


## Material one-liners
[isitemblock](Skills-Conditions-isitemblock), [isitemedible](Skills-Conditions-isitemedible), [isitemflammable](Skills-Conditions-isitemflammable), [isitemfuel](Skills-Conditions-isitemfuel), [isiteminteractable](Skills-Conditions-isiteminteractable),
[isitemoccluding](Skills-Conditions-isitemoccluding), [isitemsolid](Skills-Conditions-isitemsolid), [isitemstackable](Skills-Conditions-isitemstackable), [isitemtransparent](Skills-Conditions-isitemtransparent),
[isitemtagged](Skills-Conditions-isitemtagged)


## Player / server / misc
[caninventoryfit](Skills-Conditions-caninventoryfit), [canfly](Skills-Conditions-canfly), [canseechatcolors](Skills-Conditions-canseechatcolors), [canseemessages](Skills-Conditions-canseemessages), [haschatfiltering](Skills-Conditions-haschatfiltering),
[hasclientweather](Skills-Conditions-hasclientweather), [hasmetadata](Skills-Conditions-hasmetadata), [haspersistentdatatag](Skills-Conditions-haspersistentdatatag), [hasplayedbefore](Skills-Conditions-hasplayedbefore),
[hasresourcepack](Skills-Conditions-hasresourcepack), [hasscoreboardtag](Skills-Conditions-hasscoreboardtag), [isbanned](Skills-Conditions-isbanned), [isserverop](Skills-Conditions-isserverop), [ispluginenabled](Skills-Conditions-ispluginenabled),
[ispressingkey](Skills-Conditions-ispressingkey), [iswhitelistenabled](Skills-Conditions-iswhitelistenabled), [istextdisplayshadowed](Skills-Conditions-istextdisplayshadowed),
[istextdisplayseethrough](Skills-Conditions-istextdisplayseethrough)


## Event-scoped
Read a skill variable a specific trigger exposes — only meaningful on a skill bound to that
trigger:

- [eggwillhatch](Skills-Conditions-eggwillhatch) — for the [eggThrow](Skills-Triggers-eggThrow) trigger.
- [willconsumefirework](Skills-Conditions-willconsumefirework) — for the [elytraBoost](Skills-Triggers-elytraBoost) trigger.


## Advancements
[hasadvancement](Skills-Conditions-hasadvancement), [hasadvancementcriteria](Skills-Conditions-hasadvancementcriteria)


## Server tick manager
[isserverfrozen](Skills-Conditions-isserverfrozen), [isserverrunningnormally](Skills-Conditions-isserverrunningnormally), [isserversprinting](Skills-Conditions-isserversprinting),
[isserverstepping](Skills-Conditions-isserverstepping), [isentitytickfrozen](Skills-Conditions-isentitytickfrozen), [canblockrandomtick](Skills-Conditions-canblockrandomtick)


## Team / scoreboard
[isteamregistered](Skills-Conditions-isteamregistered), [isobjectivemodifiable](Skills-Conditions-isobjectivemodifiable)


## Structure blocks
[structureexists](Skills-Conditions-structureexists)


## NBT
[hasnbttag](Skills-Conditions-hasnbttag)


## Per-player sidebar (FastBoard)
[isboardon](Skills-Conditions-isboardon)


## Persisted regions
[regionexists](Skills-Conditions-regionexists), [inregion](Skills-Conditions-inregion), [isregionowner](Skills-Conditions-isregionowner), [isregionmember](Skills-Conditions-isregionmember)


## Recipes
[hasdiscoveredrecipe](Skills-Conditions-hasdiscoveredrecipe)


## MythicEnchants
Full condition surface for MythicEnchants integration. Most item-checking conditions below share
a `slot=` config field (`hand` (default), `offhand`, `head`, `chest`, `legs`, `feet`) selecting
which equipment slot's item to check.

- [ismenchregistered](Skills-Conditions-ismenchregistered) — true if an id is a registered MythicEnchants enchantment.
- [hasmenchenchant](Skills-Conditions-hasmenchenchant) — true if an item carries a given enchantment at or above a level.
- [ismenchenchanted](Skills-Conditions-ismenchenchanted) — true if an item carries any MythicEnchants enchantment.
- [hasmenchstoredenchant](Skills-Conditions-hasmenchstoredenchant) — true if an item (e.g. a book) carries a given stored enchantment.
- [ismenchenchanttooltiphidden](Skills-Conditions-ismenchenchanttooltiphidden) — true if an item's real enchantment tooltip is hidden.
- [ismenchenchantvalidfor](Skills-Conditions-ismenchenchantvalidfor) — true if a given enchantment is valid for an item.
- [ismenchcursed](Skills-Conditions-ismenchcursed) — true if an enchantment id (or an item's enchants) are cursed.
- [ismenchtreasure](Skills-Conditions-ismenchtreasure) — true if an id is a treasure-only enchantment.
- [ismenchtradeable](Skills-Conditions-ismenchtradeable) — true if an id is a villager-tradeable enchantment.
- [menchcounterrange](Skills-Conditions-menchcounterrange) — true if a MythicEnchants counter's value matches a range expression.
- [hasmenchpdc](Skills-Conditions-hasmenchpdc) — true if an item has a MythicEnchants-namespaced PDC value under a key.
- [matchesmenchitemref](Skills-Conditions-matchesmenchitemref) — true if an item matches a single prefixed custom-item ref.
- [ismenchenabled](Skills-Conditions-ismenchenabled) — true if an enchantment's effects are enabled.
- [ismenchreagentdeclared](Skills-Conditions-ismenchreagentdeclared) — true if a key has a declared reagent definition.
- [menchmobenchantoverride](Skills-Conditions-menchmobenchantoverride) — checks a mob's per-mob applicability override for an enchantment.
- [menchhasmoboverrides](Skills-Conditions-menchhasmoboverrides) — true if a mob has any ApplicableEnchants overrides defined.
- [hasmenchvanillabindingcurse](Skills-Conditions-hasmenchvanillabindingcurse) / [hasmenchvanillavanishingcurse](Skills-Conditions-hasmenchvanillavanishingcurse) — true if an item is marked with a vanilla curse by MythicEnchants' tracking.
- [ismenchanvilflag](Skills-Conditions-ismenchanvilflag) — checks an anvil/grindstone boolean config flag.
- [ismenchmigrated](Skills-Conditions-ismenchmigrated) — true if an enchant has a configured migration target.
- [ismenchorphaned](Skills-Conditions-ismenchorphaned) — true if an enchant is orphaned/stale.
- [ismenchenchantabletag](Skills-Conditions-ismenchenchantabletag) — true if a ref is a recognized enchantable tag.
- [ismenchtableenabled](Skills-Conditions-ismenchtableenabled) — true if the custom enchanting table feature is enabled.


## Java reflection (Premium)
- [javacheck](Skills-Conditions-javacheck) — evaluates a static Java method or field via reflection and compares it against an expected value. See [Extension Scripting](Skills-extensions) for the full reflection/extension guide.


## See Also
- [Scripts](Skills-Scripts) — how conditions fit into a script's `Skills:` list.
- [Mechanics](Skills-Mechanics) — StarScript's custom mechanics.
- [Targeters](Skills-Targeters) — StarScript's custom targeters, including one that filters targets by a condition list.
- [Extension Scripting](Skills-extensions) — write your own conditions in Java/JS (Premium).
