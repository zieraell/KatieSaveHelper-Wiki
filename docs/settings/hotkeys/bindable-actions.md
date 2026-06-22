---
title: Bindable Actions
parent: Hotkeys
nav_order: 1
---

Options to change the keys that trigger the various actions of the mod

<br>

The values for every config setting listed below can be any [*Key Code*](../../settings/common-input-types/enum/key-code.md)

There are *four* hotkeys that will normally be bound to a key by default. However, if you have other mods installed when this mod's config file is being generated, no hotkeys will be bound to a key by default.

### Quick Actions

* *`QuickSave_Key`*: Key used to *manually* save the current game data to it's respective save file

    * The default value is ***'F1'***

        <sub>⚠️ If this hotkey is used at any point during a speedrun submitted to the game's <a href="https://www.speedrun.com/dreambbq" target="_blank" rel="noopener noreferrer">*speedrunning leaderboard*</a>, the run will not be verified</sub>

* *`ReloadConfig_Key`*: Key used to reload all of the mod's settings from its config file

    * The default value is ***'F4'***

* *`ToggleGameAutoSaving_Key`*: Key used to toggle the game's auto saving feature on and off

    * The default value is *'None'*

        <sub>⚠️ If the game's autosaving feature is forcibly disabled at any point during a speedrun submitted to the game's <a href="https://www.speedrun.com/dreambbq" target="_blank" rel="noopener noreferrer">*speedrunning leaderboard*</a>, the run will not be verified</sub>

* *`LogCurrentSeedInfo_Key`*: Key used to log all of the currently active seeds, along with the in-game events they trigger, to the modloader console log

    * The default value is *'None'*

### Reloading Saves

* *`ReloadSaveWithFileSeed_Key`*: Key used to reload the current save normally, using the seed from it's respective save file

    * The default value is ***'F2'***

* *`ReloadSaveWithCurrentSeed_Key`*: Key used to reload the current save with the currently loaded seed

    * The default value is *'None'*

* *`ReloadSaveWithNewSeed_Key`*: Key used to reload the current save with a new seed generated using the method specified in the 'Save Seed Generator' config setting

    * The default value is *'None'*

    <sub>(Note that *reload* actions do not modify the seed value inside the save file, at least until an *auto* or *manual* save is triggered)</sub>

### Resetting Saves

* *`ResetSaveWithFileSeed_Key`*: Key used to immediately erase the current save, create a new empty one in the same slot that has the erased save file's stored seed, then load it

    * The default value is ***'F3'***

* *`ResetSaveWithCurrentSeed_Key`*: Key used to immediately erase the current save, create a new empty one in the same slot that has the currently loaded seed, then load it

    * The default value is *'None'*

* *`ResetSaveWithNewSeed_Key`*: Key used to immediately erase the current save, create a new empty one in the same slot that has a new seed (generated using the method specified in the 'Save Seed Generator' config setting), then load it

    * The default value is *'None'*

### Warping Through Scenes

* *`WarpToNextScene_Key`*: Key used to immediately warp to the next scene from the game's internal scene list

    * The default value is *'None'*

* *`WarpToPreviousScene_Key`*: Key used to immediately warp to the previous scene from the game's internal scene list

    * The default value is *'None'*

* *`WarpToNextEntrance_Key`*: Key used to immediately warp to the next scene entrance within the currently loaded scene

    * The default value is *'None'*

* *`WarpToPreviousEntrance_Key`*: Key used to immediately warp to the previous scene entrance within the currently loaded scene
 
    * The default value is *'None'*

### Main Menu Shortcuts

* *`ExitToSaveSelect_Key`*: Key used to immediately exit the current save to the *Save Select* screen in the *Main Menu*

    * The default value is *'None'*

* *`ExitToSaveSelectAndEraseSave_Key`*: Key used to immediately erase the current save and exit to the *Save Select* screen in the *Main Menu*

    * The default value is *'None'*