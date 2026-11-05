# Changelog

## 0.2.5
- New Docks tab in the Mining Unit window (F4): one card per dock with a status icon, who uses it, what for, and how long.
- Each dock lists up to 3 waiting ships, then "+n waiting". Every waiting ship shows why it waits: zz (waiting), cargo % (green/yellow/red), fuel low, or waited too long, plus whether it is flying to the dock or holding near it.
- A "?" button explains every icon and colour.
- Columns wrap long names instead of overlapping.
## 0.2.4
- Emergency Stop in single-ship mode now stops only the selected ship (All ships mode still stops everyone).
- A ship that keeps failing to reach a rock now gives up after a few tries instead of retrying forever.
- When a flight is still blocked right after a detour, the ship skips that rock and picks another.
- The collision brake is less touchy under load, and blocked-path strikes only count when they happen back to back.
- The Mining Unit window (F4) can no longer get stuck unable to reopen after a close.

## 0.2.3
- Miners keep mining until the rock is gone or cargo is nearly full; a rock that gives no ore is no longer re-picked in a loop.
- Smarter flying: ships check the path for rocks, steer around them with one waypoint, and slow down only for the last 500 m. Settings `path_clearance_m` and `bubble_clearance_m` (config file).
- All our flights longer than the warp trip distance now warp (same system), including cleaner sweeps. Cleaner sweeps skip ore in other sectors and no longer get stuck on the return warp.
- Faster start: a rock registry is built from the save and cached to disk (MiningRegistryCache.bin), so restarts load in seconds.
- Power: a ship that loses power (empty reactor) goes to refuel; refuel no longer forces an unload below 90% cargo. Far enemies that target a ship no longer make it flee: new setting `flee_target_range_km` (default 5).
- Safer: F4 toggle closes safely, a freeze watchdog writes MiningFreeze.txt, new debug commands for modders.

## 0.2.2
- Miners no longer get stuck mining a rock that gives no ore: a ship now gives up after 30 s without ore, collects what is floating, and moves on. A rock that gives nothing three times is skipped, and the ship stops with a clear message if no rock is left.
- Miners stop at 90% cargo instead of 100% and go to unload.
- Fleeing: a miner now flees to the dock when an enemy targets it, not only after it is hit. New setting `flee_on_target` in the config file (default on).
- A **combat log** (MiningCombat.txt) records who attacked a ship, hull drops and ship losses.
- Destroyed ships are removed from the ship list and controls; their log stays in the Log tab (All ships) marked "(destroyed)".
- Ships no longer wait forever: a failed or looping dock retry, a rock that keeps vanishing, or a 15-minute wait for a dock now stops the ship with a message.
- Settings are checked: values outside the allowed range are rejected in the Operation tab and clamped in the config file. Refuel amount can no longer be set below its threshold.
- Fixed the mod switching itself off ("safe mode") and stopping all miners while the Collect button was running.

## 0.2.1
- Far trips are faster: when a ship has to fly more than a set distance to a dock (new **Warp trip distance (km)** setting in the Operation tab, default 5), it warps most of the way if it has fuel, then docks. Docks in another sector are still reached by autopilot.
- A slow ship no longer gives up on a dock trip while it keeps getting closer: the dock timeout restarts each time the ship gets 500 m nearer.
- Fixed an error when opening the Mining Unit window (F4), including the window failing to open after a long play session.

## 0.2.0
- New **Collect ore** button (Actions box): the ship picks up all the floating ore around it, nearest first, without mining. The button shows how many floating ores there are ("Collect 9700 ores"). When the cargo fills up it docks, unloads and comes back to continue.
- Miners no longer leave floating ore behind: a ship whose cargo is full (including a partly filled last stack) goes to unload instead of mining on, and collects leftover ore before leaving a rock.
- Much less lag: rock searching is cached, and the floating-ore scan runs once a minute for the whole fleet.
- **Unload** now visits every unload dock it needs: each ore goes to its own dock, one dock after another, until the cargo is empty. The per-ore unload switches are gone: an ore is unloaded when it has an unload dock. "Nothing to unload" and "no unload dock for <ore>" are shown clearly.
- New **dock control**: ships no longer fight over docks. Waiting ships go to a line near the dock and are called in one by one: fullest cargo first, then low fuel, and anyone waiting 10 minutes goes first. A ship with cargo that needs fuel unloads first. Parked, empty or full ships leave a dock when another ship is waiting. A full dock is skipped and the next dock is tried.
- New **Docks** tab: every dock with its status, who is using it, and who is waiting.
- The wait text now says what the ship waits for: "Waiting for Unload Silica 1 (2:09 occupied by Cleaner)". Docks and ships are shown by name.
- A ship that is docked now undocks first before flying to another dock (it used to sit still), and a ship that really cannot move shows a red message instead of staying silent.

## 0.1.6
- Fixed the FPS that kept dropping the longer you played with the mod loaded.
- Miners now find ores that have no rock loaded near you (for example silica): the ship loads the area around the nearest rock and goes mining there. Works for large and small asteroids.
- The game no longer crashes when you close it.
- Rock searching is shared between all ships and refreshes once a minute instead of every few seconds.

## 0.1.5
- Ship tab: the refuel and unload dock lists no longer stop at 5 docks. Add as many as you need; each list grows with your docks.
- Ship tab: removed the extra "Refuel dock" field at the top (the Refuel docks list below replaces it).
- Items tab: the resource queue is no longer limited to 20 rows.
- Log tab: no longer limited to 60 lines.

## 0.1.4
- Ship tab: unload docks are now chosen per ore. Each enabled ore has its own card where you add up to 5 docks; the ship uses the first free one. An ore with no dock is not unloaded and the ship shows a yellow warning.
- Ship tab: refuel now also takes a list of docks (first free one wins), next to the single Refuel dock.
- Dock cards show the ore or fuel icons, and the ore cards start with Water Ice.
- The single Unload dock selector is gone: add docks to the ore cards again after updating.

## 0.1.3
- Dock lists show your renamed docks (industrial and station docks) and no longer list the docks on ships. Names refresh while the window is open.
- Ship picker: one click selects a ship, a fleet or all ships. The tick boxes are gone.
- Operation tab: new **Warp range** (default 50 km): a rock farther than this is not flown to, the ship warps to another sector instead. Radius, mining distance and max radius now show their unit and default to 50 km, 50 m and 50 km.
- Operation tab: hover any field or check for an explanation.
- Safety checks after game updates (the mod switches a feature off instead of misbehaving) and performance fixes.

## 0.1.2
- Renamed "Belt" to **Sector** everywhere the player sees it: the button now reads **Warp to sector**, and status and log messages say sector.

## 0.1.1
- Version bump to verify the MSCore updater. No gameplay changes.

## 0.1.0 - First public release
- Mining Unit block with its own window, plus the F4 fleet window.
- Automatic per-ship mining loop: mine, dock, unload, refuel, repeat.
- Resource queue (20 rows) with repeat and unlimited amounts.
- Dock waiting with retries, dock time limit, fuel rules.
- Sector Travel: nearest-rock-first mining; sector warp only when nothing is in range; goes home and idles when no sector has ore.
- Per-ship settings with defaults, status panel and log tab.
- Installs and updates through MSCore Manager.
