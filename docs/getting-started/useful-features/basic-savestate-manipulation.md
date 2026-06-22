---
title: Basic Savestate Manipulation
parent: Useful Features for Speedrunning
nav_order: 1
---

### Relevant Hotkey Options

* You can immediately load into a fresh save that overwrites the loaded save slot with the various `ResetSave` hotkeys.

    * The `ResetSaveWithFileSeed` hotkey is bound to the ***F3*** key by default.

* You can immediately load into the game again from the loaded save slot's file data using the various `ReloadSave` hotkeys.

    * This is basically the same as exiting to the Main Menu and loading the save slot again.

    * The `ReloadSaveWithFileSeed` hotkey is bound to the ***F2*** key by default.

* While loaded into the game, you can warp to any area you would like using the `Warp` hotkeys.

    * To warp back and forth between the list of areas, use the `WarpToNextScene` and `WarpToPrevScene` hotkeys

    * To warp back and forth between the list of *entrances* to an area, use the `WarpToNextEntrance` and `WarpToPrevEntrance` hotkeys.

    <sub>(None of these hotkeys are bound to a key by default)</sub>

    <br>

* The game can be *manually* saved with the `QuickSave` hotkey.

    * Both *auto* and *manual* saves will store the last area and entrance you warped to as the new spawn point when loading the save.

    * This is bound to the ***F1*** key by default.

* You can toggle the game's *autosaving* feature *on* and *off* using the `ToggleGameAutoSaving` hotkey.

    * If you would like the *autosaving* to be disabled automatically when the game is started, set the `GameAutoSavingDisabledByDefault` config setting to ***'true'***

    * This is not bound to a key by default.

<br>

### Example: Practicing "Purple Guy" on a Fresh Save

1. Load into the Save

2. Use the `Warp` hotkeys to teleport to the *BackdoorFromHub* entrance in the *USBright* area

3. *Manually* save the game with the `QuickSave` hotkey

4. Feel free to practice, use the `ReloadSaveWithFileSeed` hotkey whenever you mess up to try again

<br>

### Example: Practicing Seeded Frogger on any Save

1. Load into the Save

2. Use the `Warp` hotkeys to teleport to the *Core*

3. *Manually* save the game with the `QuickSave` hotkey

4. Disable the game's *autosaving* feature with the `ToggleGameAutoSaving` hotkey

5. Feel free to practice, use the `ReloadSaveWithFileSeed` hotkey whenever you fall in the river to try again
