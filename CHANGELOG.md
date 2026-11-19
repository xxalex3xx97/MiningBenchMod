# Changelog

## 0.2.22

- Needs MSCore 0.8.12 (update MSCore first).
- **Mining beams no longer hurt your own ships.** The mining laser damages any ship in its beam, which looked like ships dying with no attacker. A mining ship now holds its laser while another ship is within 300 m, and gives up that rock after 15 s and picks another. Other ships' flight plans treat a mining ship as a 300 m no-go zone, and ships do not pick rocks inside it.
- **Fleeing works.** A ship hit with no attacker now really flees: it is no longer stopped a moment after it starts, it flies to a parking dock like a normal trip, and the log line reads "Fleeing: ..." instead of a red ERROR.
- **Shield and hull log** now shows the real shield values.
- **Fixed** "dock job already running for this ship" when a dock was granted while the ship was still flying to a parking dock.
- Not run in game yet: the shield value line during a fight.

## 0.2.21

- **Misc docks.** New "Misc docks" list in the F4 Ship tab. Anything a ship carries that has no dock of its own (non-ore items, or ores with an empty dock list) is unloaded at a misc dock, always after the ore docks. Name a dock `[MISC]` to add it automatically.
- **Parking docks and a Park button.** Name a dock `[PARKING]` (or add one in the new Parking docks list). Ships park there after Stop loop, when they have nothing to do, while waiting in a dock queue (they keep their place) and after a flee. New **Park** button in the Actions box. EMERGENCY STOP still freezes the ship.
- **Refuel tags.** Name a dock `[REFUEL]` to make it a refuel dock, plus `[HYDROGEN]`, `[DEUTERIUM]` and/or `[WARP]` for the fuels it supplies (none = all). A ship picks a refuel dock that has the fuel it needs.
- **Ship name tags.** Put `[TITANIUM]` in a ship's name and it mines titanium until the cargo is full; `[TITANIUM:200]` mines 200. Several tags make an ordered queue (`[NICKEL:100] [TITANIUM:50]`). `[ICE]` works for water ice. Editing the Items tab now rewrites these tags in the ship's name, so the name always shows what the ship does.
- **Items tab.** In All ships or a fleet, ships are grouped by ore with counts; an edit applies to that group only. New presets: save a queue under a name and apply it to a ship, a group or all ships.
- **New window layout.** Dock cards are collapsible with the Add dock button in the header and a `?` button that explains the name tags. Dock rows show how many ships use them. The Docks tab groups docks by type, the Log tab has one collapsible card per ship, grouped by fleet. Docks you pick by hand are grouped too.
- **Fixed** the game hanging while a save was loading with ships mining.

## 0.2.20

- Needs MSCore 0.8.11 (update MSCore first).
- **Dock tags:** name a dock with the ore in square brackets, capitals, e.g. `[TITANIUM]`, `[NICKEL]`, `[SILICA]`. The dock is added first to that ore's unload list of every ship, and shows in the Ship tab already selected and locked (it cannot be removed unless you rename the dock without the tag). Docks you pick by hand come after them.
- **[AUTO-FILTER]:** a dock with `[AUTO-FILTER]` and one ore tag gets its filter set to that ore on every port.
- **[MISC]:** a dock named `[MISC]` takes anything that has no ore dock of its own (not filtered; not tested in game yet).
- One ore tag per dock only. A dock with two or more ore tags is ignored (one log line names it).
- Fixed: a crash when the Mining Unit window and the dev menu were opened in turn.
- The mining ships' sector and rock lookups use MSCore's class names, so a game update that renames them needs only an MSCore fix.

## 0.2.19

- Needs MSCore 0.8.7: ships far from you are now kept loaded by MSCore, so a game update that moves its internals no longer breaks far mining inside this mod. With an older MSCore the mod still mines, but far ships may stop; update MSCore first.
- Fixed: the Mining Unit window keybinds keep working if a game update renames the window toggle.

## 0.2.18

- Fixed: ships being destroyed for no visible reason. Two ships could pick the same rock and keep ramming each other. A rock is now taken by one ship at a time.
- New safety net: when a ship takes hull or shield damage with no attacker, all other mining ships stop, the hit ship flies to a dock, and 10 seconds later the others resume what they were doing. After three such stops in 5 minutes it falls back to the normal flee.
- Fixed: ships far from you stay readable on the latest game update, and a ship waiting in a far sector no longer stalls.

## 0.2.17

- Works with the new game build again: a far-away mining ship no longer stops with "ship actor unreadable".
- Mining ships far from you now load only their own sector chunk to stay readable, instead of a larger area.

## 0.2.16

- Fixed: the game could crash when loading a save after the latest game update. The Mining Unit block and research data was rebuilt for the new game version, and the research card icon shows again.

## 0.2.15

- Fixed: the Mining Unit was missing from the research tree and could not be placed on a ship. The research, block and model files were left out of the 0.2.7 to 0.2.14 downloads and are included again.

## 0.2.14
- Fleeing is fixed: a ship that is attacked now really leaves. It warps away to a safe spot outside the base, waits there, then queues for a dock and docks.
- Losing shields now makes a ship flee, not only losing hull.
- Fleeing no longer cancels itself on repeat hits, and works with an empty cargo and with any dock.
- If the warp cannot start under fire, the ship uses an instant warp instead of crawling to the dock.

## 0.2.7
- Fixed: the game could freeze or crash when you loaded a save from the main menu with the mod installed. The mod now recognises a new game world and drops what it knew about the old one, before it reads anything.
- Warping no longer makes the mod forget the rocks: only a real world load (menu, load a save) does. After a load it picks up again within a few seconds.
- A short failed read of the player no longer counts as "world gone": it takes about a second of failures in a row.
- After a rare internal fault the mod recovers in seconds instead of staying blind for up to 10 minutes.
- Tested in game (2026-11-08): menu to load a save several times, warping with a mining ship, and a long session.
## 0.2.6
- New Mining Unit model: a bench with two angled monitors, an AI screen on the left and a rock on the right, in the game's white and orange look.
- Includes the Mining Unit block and its research unlock, so it works on a fresh install.

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
