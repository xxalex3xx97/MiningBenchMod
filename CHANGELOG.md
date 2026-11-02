# Changelog

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
