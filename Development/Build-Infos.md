Somewhat digested version of a changes history.

This section is probably not complete ever, but it can give a quick overview what parts to adapt or regenerate.

The builds marked as _mostly stable_ are considered very stable and should be preferred over all previous development builds. Usually development builds get marked as _mostly stable_ after having been around for a while, and possibly before a more shifty phase with new additions or changes with uncertain stability. Some builds marked "mostly stable" are also marked as 'recommended' (star) on Jenkins, which means something like they're actually pretty good and can be considered worth a beta release at least. 

Broken builds usually are marked as _broken_ or _deficient_ or get removed from Jenkins. They should not appear in this list.

For a complete list of changes grouped by build number see:

http://ci.md-5.net/job/NoCheatPlus/changes

Complete list of changes on GitHub:

https://github.com/NoCheatPlus/NoCheatPlus/commits/master

**Quick overview over the latest notable builds:**

https://github.com/NoCheatPlus/Docs/wiki/Notable-Builds

----

### 3.15.0-SNAPSHOT-sMD5NET-b1020(cumulative)
* New
 * MC 1.10 support.
 * Basic vehicle fly checks for more than boats.
 * Ability and configuration for loading chunks for moving, teleport and world change.
 * Hot fix for 1.9/1.10 falling block duplication with end portals.
 * The moving.passable check now accounts for the full bounds of a player.
 * Overall packet frequency check for pre-1.9 (ProtocolLib).
* Configuration
 * Remove compatibility.blocks.ignorepassable (use overrideflags instead).
 * Add default entry for piston_moving_piece (overrideflags).
 * Kick messages for illegal player and vehicle moves are configurable.
* Fixes
 * Passable: Fix moving on soil (1.10.x).
 * SurvivalFly: Fix climbing up trap door above ladder.
 * Fix block flags for for fence-like blocks.
 * Fix low food level sprinting with players who are allowed to toggle flight.
 * Vehicles: falling with minecarts.
 * Confine climbing speed more.
 * Reactivate net.sounddistance for 1.9 and later.
 * Update the CB-Reflect module for past 1.9.
 * Attempt to fix issues with fake players with fight checks.
 * (Attempt to improve ladder/vine + velocity.)
* Other changes
 * Remove compatibility module for Glowstone (legacy).
* Internals
 * [BREAKING] Change build profiles: ncp_base must be active always.
 * [BREAKING] Moving classes/interfaces around.
 * [BREAKING] MCAccess: split off more fine grained providers.
 * Extend debug logging for blockinteract (rate-limited).
 * Add build profile for 1.7_r4 (MC 1.7.10).

### 3.14.0-SNAPSHOT-sMD5NET-b989(mostly stable, cumulative)
* Release type: **mostly stable**
* Supported versions of Minecraft (CraftBukkit/Spigot)
 * Focus: 1.9.4
 * Supported: 1.4.5-R1.0 - 1.9.4
* Download at Jenkins: http://ci.md-5.net/job/NoCheatPlus/989/
* Hashes
 * MD5: f14bcc06f982d4d75750e36897716820
 * SHA512: 73565272d83ca943118cbd8cea9891dc02fab1a539c26f8cb909ea7b3fefc5e92ea0e2f07901a2209e2f64f47ca6d96da986f4b4c1a9f6aa919eb76ad60c6ce9
 * File size: 1165971
* New
 * MC 1.9.4 compatibility.
 * Basic boat fly check.
 * Exempt NPCs from all checks by default.
 * 'ncp stopwatch' for testing.
* Configuration
 * Create a new vehicle section, change related paths.
 * The temporary login denial message is now configurable (strings.msgtempdenylogin).
 * Configure exemption by meta data and exemption for NPCs.
 * Add configuration for boatsanywhere (place on land).
 * Change default for 'ignoreallowflight' to true.
* Fixes
 * Sweep attack detection (AoE).
 * StackOverflowError with inventory.open and a blacklist kick by WorldGuard.
 * NoFall: Skip dealing damage to players who are allowed to fly.
 * SurvivalFly: Fix climbing up trap door above ladder. (partial)
 * Prevent another variant of packet-based speeding.
 * Vehicles: Fix vehicle detection for missing vehicle events.
 * Vehicles: set-back handling.
 * Support higher levels of the levitation effect.
 * Improve vertical piston support (not finished, not yet officially activated).
 * TO BE TESTED: Allow vertical velocity on ladders and vines (once).
 * Account for off hand in (hopefully) all relevant places.
 * Also recognize ProtocolLib versions just with build number prefix.
 * Do not check for meta data off the primary thread.
* Internals
 * Debug only: unused vertical velocity tracking.
 * [BREAKING] Larger refactoring and changes for vehicle fly checks (mostly unify/change location and set-back handling).
 * Hard teleport on vehicle set-backs by default, from within other event handling.
 * Location trace doesn't merge entries anymore (fight / latency).
 * Extend/alter debug logging.
 * Added GPLv3 headers to source files.

### 3.14.0-SNAPSHOT-sMD5NET-b960(mostly stable, cumulative)
* MC 1.9
 * Blocks break data and flags.
 * Dedicated MCAccess module for CB with MC 1.9.
 * Allow standing on shulkers.
 * Rough levitation support.
 * Very coarse elytra support, hardly safe vs. abuse. _Note recent configuration overrides (not advertised!)._
 * Allow versions of ProtocolLib with MC 1.9 (currently disable SoundDistance): 3.7, 3.7.0, 4.0.0 or later.
 * Ignore sweep attack follow up damage.
 * "Noob tower": jumping upwards, building underneath.
 * Ignore multi-block place of bedrock and ender crystals.
 * Block place: check the placed material instead of what's in main hand, if available.
 * Disable FastHeal with MC 1.9.
 * (Still enable the pvp-knockback workaround with MC 1.9.)
* Configuration
 * Change creativefly model configurations (default speeds for elytra and spectator).
 * Increase hover login ticks to 60 (previously 0).
* Fixes
 * More cases with splashing through water.
 * creativefly
  * Fix violation skipping/cooldown mechanics. This might increase violation levels.
  * Fix set back handling (maxheight).
  * Fly-nofly transition: Reduce [ERROR].
 * Player instances stored wrongly.
* Internals
 * Add more minimized build profiles to pinpoint Spigot 1.8.8/1.9.
 * Organize some workaround code better.
 * Extend/alter debug logging.

### 3.13.8-SNAPSHOT-sMD5NET-b930(cumulative)
* New
 * A quick check for extreme moves.
* Fixes
 * Portal events: only clear data if a location is present, add debug log.
 * FastClick: Don't add violation twice for display.
 * Fix HashMapLow (bucket position).
* Changes
 * Handle system time running backwards differently.
 * Adjust log message for ProtocolLib.
* Internals
 * [BREAKING] Add a penalty framework. Breaks internal API, see commit messages and diffs.
 * Catch unintended input somewhere.

----
For older builds see: https://github.com/NoCheatPlus/Docs/wiki/Old-Builds

For very old builds see: https://github.com/NoCheatPlus/Docs/wiki/Very-Old-Builds
