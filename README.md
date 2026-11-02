<div align="center">

# Mining Unit

### Automatic mining fleets for *Main Sequence*

[![Latest release](https://img.shields.io/github/v/release/xxalex3xx97/MiningBenchMod?style=for-the-badge&label=release)](https://github.com/xxalex3xx97/MiningBenchMod/releases/latest)
![Requires](https://img.shields.io/badge/requires-MSCore%200.5.0%2B-blueviolet?style=for-the-badge)
![Game](https://img.shields.io/badge/game-Main%20Sequence%20Demo-orange?style=for-the-badge)

**Set a ship to mine, and it mines, refuels, unloads and repeats - on its own.**

</div>

---

## What is it?

*Mining Unit* adds a **Mining Unit** building and a control window to the game. Pick your ships, tell them what to mine, and each ship runs its own mining loop: find a rock, fly to it, mine, return to a dock when it is full or low on fuel, unload, refuel, and go again.

## Features

- **Mining Unit block + window** - place the block and press **F** to open its control window, or press **F4** anywhere for the fleet window.
- **Per-ship mining loops** - every ship runs independently. Start or stop one ship, or all of them.
- **Resource queue** - a list of up to 20 rows (resource + amount). Ships mine them in order and can repeat the list. Amount `0` = unlimited.
- **Smart docking** - docks when cargo is full or fuel is low, unloads, refuels, then resumes where it left off. A busy dock shows **Waiting for dock** and retries automatically.
- **Fuel handling** - minimum/maximum fuel rules and a refuel dock.
- **Sector Travel** - nearest rock first; only warps to another sector when nothing is in range. If no sector has ore, the ship goes home and idles instead of looping forever.
- **Dock time limit** - stops a ship that sits docked too long and shows an error.
- **Status and log** - live status per ship (what it is mining, ETA, cargo, speed) plus a log tab.
- **Quick actions** - Dock, Undock, Refuel, Unload and an **Emergency stop** for any ship.
- **Fully configurable** - radius, mining distance, idle and wait times, ore toggles with icons, saved per ship, with *Set as default*.

## Installation

Mining Unit needs the **MSCore** mod loader.

1. Close the game.
2. Get **MSCoreManager.exe** from [MSCore releases](https://github.com/xxalex3xx97/MSCore/releases/latest) and run it.
3. Click **Install/Repair MSCore** (first time only).
4. Click **Add mod...** and enter
   `https://github.com/xxalex3xx97/MiningBenchMod`
5. Start the game.

To update later, open the manager, click **Check**, then **Update selected**. To uninstall, select the mod and click **Remove mod**: the mod and its UI are removed together, your settings and logs stay.

## Using it

1. Build/place a **Mining Unit** and press **F** on it (or press **F4**).
2. Choose a ship, set its **Ship** tab (dock, refuel dock), **Items** tab (what to mine) and **Operation** tab (radius, fuel, ore toggles).
3. Press **Start loop**. Use **Stop loop** to finish the current trip and park, or **Emergency stop** to halt immediately.

## Notes

- Built for the *Main Sequence Demo*. It uses unofficial modding tools, so a game update can break it until the mod is updated.
- Settings are stored in `MiningBench.ini` and are never overwritten by updates.
- This is an unofficial community mod, not affiliated with the game's developers.

See [CHANGELOG.md](CHANGELOG.md) for what changed in each version.
