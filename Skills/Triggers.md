## Introduction
Scripts react to events via `~onX{config}` tokens on a `Skills:` line — StarScript's own
trigger catalog (below) covers gaps in Skript-style event coverage; on top of that, scripts can
ALSO react to any MythicMobs-native trigger directly by using MM's own trigger name as the token
(e.g. `~onDamaged`, `~onEnterCombat`, or any addon-registered trigger) — there is no need to wrap
or duplicate MM's own triggers.

Multiple `Skills:` lines sharing the same trigger token fire together on that event. A line with
no trigger token runs on every event this script is bound to.


## Session
[join](Skills-Triggers-join), [quit](Skills-Triggers-quit), [respawn](Skills-Triggers-respawn), [worldChange](Skills-Triggers-worldChange), [gamemodeChange](Skills-Triggers-gamemodeChange)


## Player
[connect](Skills-Triggers-connect), [kick](Skills-Triggers-kick), [localeChange](Skills-Triggers-localeChange), [bedEnter](Skills-Triggers-bedEnter), [bedLeave](Skills-Triggers-bedLeave), [deepSleep](Skills-Triggers-deepSleep),
[flightToggle](Skills-Triggers-flightToggle), [jump](Skills-Triggers-jump), [armSwing](Skills-Triggers-armSwing), [riptide](Skills-Triggers-riptide), [elytraBoost](Skills-Triggers-elytraBoost), [swapHands](Skills-Triggers-swapHands),
[itemBreak](Skills-Triggers-itemBreak), [itemDamage](Skills-Triggers-itemDamage), [itemMend](Skills-Triggers-itemMend), [eggThrow](Skills-Triggers-eggThrow), [bookEdit](Skills-Triggers-bookEdit), [harvestBlock](Skills-Triggers-harvestBlock),
[armorChange](Skills-Triggers-armorChange), [stopUsingItem](Skills-Triggers-stopUsingItem), [readyArrow](Skills-Triggers-readyArrow), [pickupArrow](Skills-Triggers-pickupArrow), [trade](Skills-Triggers-trade),
[resourcePack](Skills-Triggers-resourcePack), [foodChange](Skills-Triggers-foodChange), [move](Skills-Triggers-move)


## Chat & commands
[chat](Skills-Triggers-chat), [command](Skills-Triggers-command)


## Movement & interaction
[interact](Skills-Triggers-interact), [interactEntity](Skills-Triggers-interactEntity), [sneak](Skills-Triggers-sneak), [sprint](Skills-Triggers-sprint), [itemDrop](Skills-Triggers-itemDrop),
[itemPickup](Skills-Triggers-itemPickup), [itemConsume](Skills-Triggers-itemConsume), [itemHeld](Skills-Triggers-itemHeld), [fish](Skills-Triggers-fish), [bucketFill](Skills-Triggers-bucketFill),
[bucketEmpty](Skills-Triggers-bucketEmpty)


## Entity & combat
[kill](Skills-Triggers-kill), [entityKill](Skills-Triggers-entityKill), [death](Skills-Triggers-death), [damage](Skills-Triggers-damage), [damageByEntity](Skills-Triggers-damageByEntity), [attack](Skills-Triggers-attack),
[shoot](Skills-Triggers-shoot), [shootBow](Skills-Triggers-shootBow), [projectileHit](Skills-Triggers-projectileHit), [heal](Skills-Triggers-heal), [combust](Skills-Triggers-combust), [resurrect](Skills-Triggers-resurrect), [targeted](Skills-Triggers-targeted),
[tame](Skills-Triggers-tame), [breed](Skills-Triggers-breed), [glideToggle](Skills-Triggers-glideToggle), [swimToggle](Skills-Triggers-swimToggle), [leash](Skills-Triggers-leash), [unleash](Skills-Triggers-unleash), [mount](Skills-Triggers-mount),
[dismount](Skills-Triggers-dismount), [entitySpawn](Skills-Triggers-entitySpawn), [explode](Skills-Triggers-explode), [lightning](Skills-Triggers-lightning), [entityKnockback](Skills-Triggers-entityKnockback),
[preSpawn](Skills-Triggers-preSpawn), [spawnerSpawn](Skills-Triggers-spawnerSpawn), [damageByBlock](Skills-Triggers-damageByBlock), [entityTrackPlayer](Skills-Triggers-entityTrackPlayer), [entityUntrackPlayer](Skills-Triggers-entityUntrackPlayer)


## Inventory / crafting / enchanting
[inventoryOpen](Skills-Triggers-inventoryOpen), [inventoryClose](Skills-Triggers-inventoryClose), [inventoryClick](Skills-Triggers-inventoryClick), [craft](Skills-Triggers-craft), [enchantItem](Skills-Triggers-enchantItem), [smelt](Skills-Triggers-smelt),
[furnaceExtract](Skills-Triggers-furnaceExtract), [anvilPrepare](Skills-Triggers-anvilPrepare)


## Blocks
[blockBreak](Skills-Triggers-blockBreak), [blockPlace](Skills-Triggers-blockPlace), [signChange](Skills-Triggers-signChange)


## Progression
[levelChange](Skills-Triggers-levelChange), [expChange](Skills-Triggers-expChange), [advancement](Skills-Triggers-advancement), [portal](Skills-Triggers-portal), [teleport](Skills-Triggers-teleport),
[statisticIncrement](Skills-Triggers-statisticIncrement)


## World / blocks / server
[blockDamage](Skills-Triggers-blockDamage), [blockDropItem](Skills-Triggers-blockDropItem), [blockFertilize](Skills-Triggers-blockFertilize), [blockIgnite](Skills-Triggers-blockIgnite), [bucketEntity](Skills-Triggers-bucketEntity),
[bellRing](Skills-Triggers-bellRing), [dispense](Skills-Triggers-dispense), [portalCreate](Skills-Triggers-portalCreate), [worldSave](Skills-Triggers-worldSave), [worldUnload](Skills-Triggers-worldUnload), [chunkLoad](Skills-Triggers-chunkLoad),
[chunkUnload](Skills-Triggers-chunkUnload), [leavesDecay](Skills-Triggers-leavesDecay), [structureGrow](Skills-Triggers-structureGrow), [vehicleEnter](Skills-Triggers-vehicleEnter), [vehicleExit](Skills-Triggers-vehicleExit),
[vehicleDestroy](Skills-Triggers-vehicleDestroy), [consoleCommand](Skills-Triggers-consoleCommand), [broadcast](Skills-Triggers-broadcast), [weatherChange](Skills-Triggers-weatherChange), [worldLoad](Skills-Triggers-worldLoad)


## Scheduled
These aren't Bukkit events — they're driven by StarScript's own scheduler.

[serverStart](Skills-Triggers-serverStart), [timer](Skills-Triggers-timer)


## Persisted regions
[regionEnter](Skills-Triggers-regionEnter), [regionExit](Skills-Triggers-regionExit)


## Recipes
[recipeDiscover](Skills-Triggers-recipeDiscover), [crafterCraft](Skills-Triggers-crafterCraft)


## MythicEnchants
[anvilPrepareMench](Skills-Triggers-anvilPrepareMench) — the vanilla anvil recomputes its result item for a MythicEnchants-tracked combine (supports [setanvilresult](Skills-Mechanics-setanvilresult) to override the result).
[menchReload](Skills-Triggers-menchReload) — MythicEnchants reloads its datapack/skills/config.
[menchTriggerFire](Skills-Triggers-menchTriggerFire) — a MythicEnchants enchantment's internal named trigger fires (requires a `trigger=` filter — see its doc page for why).


## See Also
- [Scripts](Skills-Scripts) — how triggers fit into a script's `Skills:` list.
- [Compound Triggers](Skills-CompoundTriggers) — combine several of these into one named
  `~onName` token, with OR/AND-any-order modes and shared conditions.
- [Mechanics](Skills-Mechanics) / [Conditions](Skills-Conditions) — StarScript's other additions.
