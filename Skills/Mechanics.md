## Introduction
StarScript scripts get every MythicMobs mechanic for free — the mechanics below are
StarScript's own additions, for gaps MythicMobs (and its addons) had no built-in equivalent for.


## Admin / Moderation
- [ban](Skills-Mechanics-ban) — bans a player.
- [pardon](Skills-Mechanics-pardon) — unbans a player.
- [kick](Skills-Triggers-kick) — kicks a player.
- [op](Skills-Mechanics-op) — sets/clears operator status.
- [pvp](Skills-Mechanics-pvp) — toggles PvP for a world.
- [whitelist](Skills-Mechanics-whitelist) — toggles the server whitelist.
- [connect](Skills-Triggers-connect) — sends a player to another backend server (BungeeCord/Velocity).
- [stopserver](Skills-Mechanics-stopserver) — shuts down the server.


## Entity state
- [persistent](Skills-Mechanics-persistent) — toggles whether an entity persists.
- [silent](Skills-Mechanics-silent) — toggles whether an entity is silent.
- [customnamevisible](Skills-Mechanics-customnamevisible) — toggles custom-name visibility.
- [allayduplication](Skills-Mechanics-allayduplication) — controls an Allay's duplication ability.
- [goathorns](Skills-Mechanics-goathorns) — controls a Goat's horns/screaming/ram.
- [pandastate](Skills-Mechanics-pandastate) — controls a Panda's animation state/genes.
- [wardendisturbance](Skills-Mechanics-wardendisturbance) — controls a Warden's anger/disturbance sensing.


## Item cosmetics
- [itemcolor](Skills-Mechanics-itemcolor) — recolors leather armor/potions/maps.
- [itemglint](Skills-Mechanics-itemglint) — forces/clears an item's enchant glint.
- [itemtooltip](Skills-Mechanics-itemtooltip) — hides/shows an item's tooltip.


## Item components
Modern (1.21.2+) per-item data-component mechanics — a 1:1 port of SkBee's item-component
expressions/sections. Every mechanic below shares a `slot=` config field (`hand` (default),
`offhand`, `head`, `chest`, `legs`, `feet`) selecting which equipment slot's item to modify.

- [foodcomponent](Skills-Mechanics-foodcomponent) — sets nutrition/saturation/can-always-eat.
- [equippablecomponent](Skills-Mechanics-equippablecomponent) — sets equip slot/sound/dispensable/swappable.
- [consumablecomponent](Skills-Mechanics-consumablecomponent) — sets eating/drinking animation, sound, consume effects.
- [toolcomponent](Skills-Mechanics-toolcomponent) — sets mining speed and per-block mining rules.
- [weaponcomponent](Skills-Mechanics-weaponcomponent) — sets melee durability cost and shield-disable duration.
- [blocksattackscomponent](Skills-Mechanics-blocksattackscomponent) — makes an item block attacks (shield-style).
- [tooltipdisplaycomponent](Skills-Mechanics-tooltipdisplaycomponent) — hides the tooltip or individual component lines.
- [attackrangecomponent](Skills-Mechanics-attackrangecomponent) — sets melee attack-reach overrides.
- [adventurepredicate](Skills-Mechanics-adventurepredicate) — sets which blocks an item can place/break in Adventure mode.
- [custommodeldatacomponent](Skills-Mechanics-custommodeldatacomponent) — sets the modern list-based custom model data.
- [deathprotectioncomponent](Skills-Mechanics-deathprotectioncomponent) — makes an item act like a totem of undying.
- [fireworkscomponent](Skills-Mechanics-fireworkscomponent) — sets a firework rocket's flight duration/explosions.
- [fireworkexplosioncomponent](Skills-Mechanics-fireworkexplosioncomponent) — sets a firework star's own explosion effect.
- [instrumentcomponent](Skills-Mechanics-instrumentcomponent) — sets a goat horn's played instrument.
- [jukeboxplayablecomponent](Skills-Mechanics-jukeboxplayablecomponent) — makes an item playable in a jukebox.
- [kineticweaponcomponent](Skills-Mechanics-kineticweaponcomponent) — sets mace-style knockback/dismount properties.
- [piercingweaponcomponent](Skills-Mechanics-piercingweaponcomponent) — marks an item as a trident-style piercing weapon.
- [potioncontentscomponent](Skills-Mechanics-potioncontentscomponent) — sets a potion item's base type/color/name/effects.
- [profilecomponent](Skills-Mechanics-profilecomponent) — sets a player-head item's owning profile/skin.
- [swinganimationcomponent](Skills-Mechanics-swinganimationcomponent) — sets the arm-swing animation played on use.
- [usecooldowncomponent](Skills-Mechanics-usecooldowncomponent) — sets the cooldown applied after using an item.
- [useeffectscomponent](Skills-Mechanics-useeffectscomponent) — sets movement effects applied while using an item.
- [bundlecontents](Skills-Mechanics-bundlecontents) — sets/adds/removes a bundle item's contents.
- [setchargedprojectiles](Skills-Mechanics-setchargedprojectiles) — sets a crossbow's loaded projectiles.
- [containercomponent](Skills-Mechanics-containercomponent) — sets a shulker-box-like item's stored contents.
- [setdamageresistant](Skills-Mechanics-setdamageresistant) — makes an item immune to a damage-type tag.
- [setdamagetypecomponent](Skills-Mechanics-setdamagetypecomponent) — overrides the damage type an item deals directly.
- [setdyedcolorcomponent](Skills-Mechanics-setdyedcolorcomponent) — sets a dyeable item's color via the data-component API.
- [setenchantablecomponent](Skills-Mechanics-setenchantablecomponent) — sets an item's enchantment value.
- [setglidercomponent](Skills-Mechanics-setglidercomponent) — marks/unmarks an item as an elytra-like glider.
- [setintangibleprojectilecomponent](Skills-Mechanics-setintangibleprojectilecomponent) — marks/unmarks a projectile as intangible.
- [setitemmodel](Skills-Mechanics-setitemmodel) — overrides an item's client-side model key.
- [setmaxstacksize](Skills-Mechanics-setmaxstacksize) — sets an item's max stack size.
- [setminattackcharge](Skills-Mechanics-setminattackcharge) — sets the minimum windup charge for a full-charge attack.
- [repaircost](Skills-Mechanics-repaircost) — sets/adds/removes an item's anvil repair cost.
- [setrepairablecomponent](Skills-Mechanics-setrepairablecomponent) — sets which materials repair an item at an anvil.
- [setstoredenchants](Skills-Mechanics-setstoredenchants) — sets an enchanted book's stored enchantments.
- [settooltipstyle](Skills-Mechanics-settooltipstyle) — overrides an item's tooltip resource-pack style key.
- [setuseremainder](Skills-Mechanics-setuseremainder) — sets the item left behind after full use.
- [clearcomponent](Skills-Mechanics-clearcomponent) — removes a given data component from an item.


## Server list
- [servericon](Skills-Mechanics-servericon) — sets the server-list favicon.
- [hidefromserverlist](Skills-Mechanics-hidefromserverlist) — hides a player from the server-list hover.
- [serverlistvisibility](Skills-Mechanics-serverlistvisibility) — globally hides the player count/hover list.
- [setmotd](Skills-Mechanics-setmotd) — sets the server-list MOTD.


## Tablist
- [settablistheader](Skills-Mechanics-settablistheader) / [settablistfooter](Skills-Mechanics-settablistfooter) — set a player's tablist header/footer.
- [settablistname](Skills-Mechanics-settablistname) — sets a player's own displayed name in the tablist.
- [cleartablist](Skills-Mechanics-cleartablist) — resets a player's tablist header/footer/name.


## Remote inventory viewing
- [openplayerinventory](Skills-Mechanics-openplayerinventory) — opens another player's real inventory (view or edit).
- [openenderchest](Skills-Mechanics-openenderchest) — opens another player's real enderchest (view or edit).


## World generation
- [worldborder](Skills-Mechanics-worldborder) — resizes/repositions a world border.
- [worldload](Skills-Mechanics-worldload) — loads/generates a world.
- [worldsave](Skills-Mechanics-worldsave) — saves/unloads a world.


## Persistent storage
- [setstorage](Skills-Mechanics-setstorage) — writes a key-value storage entry.
- [getstorage](Skills-Mechanics-getstorage) — reads a key-value storage entry into a skill variable.
- [removestorage](Skills-Mechanics-removestorage) — deletes a key-value storage entry.
- [incrementstorage](Skills-Mechanics-incrementstorage) — adds/subtracts from a numeric storage entry.


## Typed variables (SQL / MongoDB / Redis)
Three parallel, independently-scoped typed variable stores — pick whichever backend fits your
setup, or use more than one at once. Unlike the persistent storage mechanics above (which default
to `scope=player`), these default to `scope=global` (suited to scoreboard-style stats, e.g.
`score_red`); all three also support `scope=skill` (per-casting-entity, mobs included, not just
players).

- [setsql](Skills-Mechanics-setsql) / [getsql](Skills-Mechanics-getsql) / [unsetsql](Skills-Mechanics-unsetsql) / [addsql](Skills-Mechanics-addsql) — SQLite/MySQL-backed (`Storage.Type`), always available.
- [setmongo](Skills-Mechanics-setmongo) / [getmongo](Skills-Mechanics-getmongo) / [unsetmongo](Skills-Mechanics-unsetmongo) / [addmongo](Skills-Mechanics-addmongo) — MongoDB-backed, opt-in via `Storage.Mongo.Enabled`.
- [setredis](Skills-Mechanics-setredis) / [getredis](Skills-Mechanics-getredis) / [unsetredis](Skills-Mechanics-unsetredis) / [addredis](Skills-Mechanics-addredis) — Redis-backed, opt-in via `Storage.Redis.Enabled`.


## JSON/YAML files
- [readjson](Skills-Mechanics-readjson) / [writejson](Skills-Mechanics-writejson) / [removejsonkey](Skills-Mechanics-removejsonkey) — read/write/delete a JSON file or key.
- [readyaml](Skills-Mechanics-readyaml) / [writeyaml](Skills-Mechanics-writeyaml) / [removeyamlkey](Skills-Mechanics-removeyamlkey) — read/write/delete a YAML file or key.


## Statistics
- [setstat](Skills-Mechanics-setstat) — sets/adds/removes/resets a player's vanilla statistic.
- [getstat](Skills-Mechanics-getstat) — reads a player's vanilla statistic into a skill variable.


## Advancements
- [awardcriteria](Skills-Mechanics-awardcriteria) — awards/revokes one advancement criterion for a player.
- [loadadvancement](Skills-Mechanics-loadadvancement) — registers a raw advancement JSON definition at runtime.


## Server tick manager
- [settickrate](Skills-Mechanics-settickrate) — sets the server's tick rate.
- [setfrozen](Skills-Mechanics-setfrozen) — freezes/unfreezes the server's tick loop.
- [sprintticks](Skills-Mechanics-sprintticks) — requests the server to sprint ticks.
- [stepticks](Skills-Mechanics-stepticks) — steps the game forward while frozen.
- [randomtickblock](Skills-Mechanics-randomtickblock) — forces one vanilla random tick on a block.


## Team / scoreboard
- [createteam](Skills-Mechanics-createteam) / [deleteteam](Skills-Mechanics-deleteteam) — register/unregister a scoreboard team.
- [teamentry](Skills-Mechanics-teamentry) — adds/removes an entry from a team.
- [setteamoption](Skills-Mechanics-setteamoption) / [setteamcolor](Skills-Mechanics-setteamcolor) / [setteamprefix](Skills-Mechanics-setteamprefix) / [setteamsuffix](Skills-Mechanics-setteamsuffix) — configure a team.
- [createobjective](Skills-Mechanics-createobjective) / [deleteobjective](Skills-Mechanics-deleteobjective) — register/unregister a scoreboard objective.
- [setobjectivenumberformat](Skills-Mechanics-setobjectivenumberformat) — sets how an objective's scores are displayed.


## Structure blocks
- [savestructure](Skills-Mechanics-savestructure) — captures a two-corner region into a structure template.
- [placestructure](Skills-Mechanics-placestructure) — places a saved structure template.
- [deletestructure](Skills-Mechanics-deletestructure) — deletes a saved structure template.


## NBT
- [getnbt](Skills-Mechanics-getnbt) / [setnbt](Skills-Mechanics-setnbt) / [removenbt](Skills-Mechanics-removenbt) — read/write/remove one NBT tag on an item.
- [mergenbt](Skills-Mechanics-mergenbt) — merges a full raw NBT compound string into an item.


## Per-player sidebar (FastBoard)
- [setboardtitle](Skills-Mechanics-setboardtitle) — sets a player's sidebar title.
- [setboardline](Skills-Mechanics-setboardline) — sets one line of a player's sidebar.
- [clearboard](Skills-Mechanics-clearboard) — clears a player's sidebar.
- [toggleboard](Skills-Mechanics-toggleboard) — shows/hides a player's sidebar.


## Persisted regions
- [createregion](Skills-Mechanics-createregion) / [deleteregion](Skills-Mechanics-deleteregion) / [resizeregion](Skills-Mechanics-resizeregion) — manage a named cuboid region.
- [setregionowner](Skills-Mechanics-setregionowner) / [addregionmember](Skills-Mechanics-addregionmember) / [removeregionmember](Skills-Mechanics-removeregionmember) — manage region owners/members.


## Recipes
Real vanilla `Bukkit.addRecipe`/`PotionBrewer` recipe registration — these show up in the actual
crafting table/furnace/stonecutter/brewing stand/recipe book, not just StarScript's own
functional GUI regions (which fall back to real vanilla recipes automatically for Workbench/
Furnace/Stonecutter, and to StarScript's own `registerbrewingrecipe` recipes for Brewing).

- [registercraftingrecipe](Skills-Mechanics-registercraftingrecipe) — registers a shaped/shapeless crafting recipe.
- [registercookingrecipe](Skills-Mechanics-registercookingrecipe) — registers a furnace/blasting/smoking/campfire recipe.
- [registerstonecuttingrecipe](Skills-Mechanics-registerstonecuttingrecipe) — registers a stonecutter recipe.
- [registersmithingrecipe](Skills-Mechanics-registersmithingrecipe) — registers a smithing-table transform recipe.
- [registerbrewingrecipe](Skills-Mechanics-registerbrewingrecipe) — registers a brewing-stand recipe.
- [registertransmuterecipe](Skills-Mechanics-registertransmuterecipe) — registers a transmute recipe (e.g. dyeing a shulker box).
- [removerecipe](Skills-Mechanics-removerecipe) — removes one recipe, or every recipe.
- [discoverrecipe](Skills-Mechanics-discoverrecipe) / [undiscoverrecipe](Skills-Mechanics-undiscoverrecipe) — locks/unlocks a recipe for a player.
- [addknowledgebookrecipe](Skills-Mechanics-addknowledgebookrecipe) / [removeknowledgebookrecipe](Skills-Mechanics-removeknowledgebookrecipe) — add/remove a recipe from a knowledge book item.
- [updateserverrecipes](Skills-Mechanics-updateserverrecipes) / [updateserverresources](Skills-Mechanics-updateserverresources) — push updated recipe/resource data to clients.


## MythicEnchants
Full mechanic surface for [MythicEnchants](https://github.com/stelliusstudio/mythicenchants)
integration, covering enchant read/write, counters, item PDC, and introspection. Most of these
share a `slot=` config field (`hand` (default), `offhand`, `head`, `chest`, `legs`, `feet`)
selecting which equipment slot's item to act on.

- [setanvilresult](Skills-Mechanics-setanvilresult) — overrides the anvil's result item during an anvilPrepareMench trigger.
- [applymenchenchant](Skills-Mechanics-applymenchenchant) / [removemenchenchant](Skills-Mechanics-removemenchenchant) — apply/remove a MythicEnchants/vanilla enchantment on an item.
- [setmenchenchanttooltiphidden](Skills-Mechanics-setmenchenchanttooltiphidden) — hides/shows an item's real enchantment tooltip.
- [copymenchenchants](Skills-Mechanics-copymenchenchants) — copies every enchantment from one item onto another.
- [snapshotmenchenchants](Skills-Mechanics-snapshotmenchenchants) / [restoremenchenchants](Skills-Mechanics-restoremenchenchants) — serialize an item's enchantments to a skill variable and restore them later.
- [createmenchbook](Skills-Mechanics-createmenchbook) — creates an enchanted book carrying given enchantments.
- [getmenchcounter](Skills-Mechanics-getmenchcounter) / [addmenchcounter](Skills-Mechanics-addmenchcounter) / [setmenchcounter](Skills-Mechanics-setmenchcounter) / [removemenchcounter](Skills-Mechanics-removemenchcounter) — read/add/set/remove a MythicEnchants player- or item-scoped counter.
- [setmenchpdc](Skills-Mechanics-setmenchpdc) / [removemenchpdc](Skills-Mechanics-removemenchpdc) / [getmenchpdc](Skills-Mechanics-getmenchpdc) — write/remove/read a MythicEnchants-namespaced PDC value on an item.
- [getmenchcustomitemid](Skills-Mechanics-getmenchcustomitemid) — reads an item's custom-item source id into a skill variable.
- [getmenchenchantlist](Skills-Mechanics-getmenchenchantlist) — writes a comma-separated enchantment id list into a skill variable.
- [getmenchrarity](Skills-Mechanics-getmenchrarity) — reads an enchantment's rarity tier id into a skill variable.
- [getmenchreagentfor](Skills-Mechanics-getmenchreagentfor) — reads the reagent key an item matches into a skill variable.
- [getmenchmythicitemtype](Skills-Mechanics-getmenchmythicitemtype) — reads an item's backing MythicMobs internal type id into a skill variable.
- [resolvemenchmythicid](Skills-Mechanics-resolvemenchmythicid) — resolves a MythicMobs item id/`mythic:` ref to its backing vanilla material name.
- [setmenchvanillabindingcurse](Skills-Mechanics-setmenchvanillabindingcurse) / [setmenchvanillavanishingcurse](Skills-Mechanics-setmenchvanillavanishingcurse) — set/clear MythicEnchants' vanilla curse tracking markers on an item.
- [getmenchanvilconfig](Skills-Mechanics-getmenchanvilconfig) — reads a numeric anvil/grindstone config value into a skill variable.
- [getmenchmigrationtarget](Skills-Mechanics-getmenchmigrationtarget) — reads an enchant's configured migration target into a skill variable.
- [getmenchconfig](Skills-Mechanics-getmenchconfig) — reads a misc MythicEnchants config/debug flag into a skill variable.
- [setmenchdebug](Skills-Mechanics-setmenchdebug) — toggles MythicEnchants' debug logging at runtime.
- [getmenchtablepower](Skills-Mechanics-getmenchtablepower) — scans a location's MythicEnchants table power into a skill variable.
- [rerollmenchenchantseed](Skills-Mechanics-rerollmenchenchantseed) — rerolls a player's enchanting-table seed.
- [invalidatemenchtableoffers](Skills-Mechanics-invalidatemenchtableoffers) — drops a player's cached enchanting-table offers.


## Java/JS reflection (Premium)
Call Java directly from any script, or run an inline JavaScript snippet — no extension bundle
needed. See [Extension Scripting](Skills-extensions) for the full guide, including writing whole
mechanics/conditions/targeters in Java or JS.

- [javanew](Skills-Mechanics-javanew) — constructs a Java object via reflection.
- [javainvoke](Skills-Mechanics-javainvoke) — calls a Java method via reflection.
- [javafield](Skills-Mechanics-javafield) — reads/writes a Java field via reflection.
- [jseval](Skills-Mechanics-jseval) — evaluates an inline JavaScript snippet (GraalJS).


## See Also
- [Scripts](Skills-Scripts) — how mechanics fit into a script's `Skills:` list.
- [Conditions](Skills-Conditions) — StarScript's custom conditions.
- [Targeters](Skills-Targeters) — StarScript's custom targeters.
- [Extension Scripting](Skills-extensions) — write your own mechanics in Java/JS (Premium).
