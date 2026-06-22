---
title: Game Tweaks
parent: Settings
nav_order: 2
---

Options to tweak the game's vanilla functionality

<br>

### Seed Generators

* *`SaveSeedGeneratorType`*: Which method the game should use to select a save seed when creating a new save

    * Values can be the name of any [*Seed Generator*](../settings/common-input-types/enum/seed-generator.md), the default value is *'Random'*

        * The *Static* generator for this *seed type* uses the value from the *`StaticSaveSeed`* config setting

* *`SessionSeedGeneratorType`*: Which method the game should use to select a session seed

    * Values can be the name of any [*Seed Generator*](../settings/common-input-types/enum/seed-generator.md), the default value is *'Random'*

        * The *Static* generator for this *seed type* uses the value from the *`StaticSessionSeed`* config setting
        
* *`HardwareSeedGeneratorType`*: Which method the game should use to select a hardware seed

    * Values can be the name of any [*Seed Generator*](../settings/common-input-types/enum/seed-generator.md), the default value is *'Device'*

        * The *Static* generator for this *seed type* uses the value from the *`StaticHardwareSeed`* config setting

* *`RegenerateSessionSeed_EventTrigger`*: Which event will trigger the game's active *Session* seed being regenerated using the method specified in the `SessionSeedGeneratorType` config setting

    * Values can be the name of any [*Event Trigger*](../settings/common-input-types/enum/event-trigger.md), the default value is *'OnHotkey'*

* *`RegenerateHardwareSeed_EventTrigger`*: Which event will trigger the game's active hardware seed being regenerated using the method specified in the `HardwareSeedGeneratorType` config setting

    * Values can be the name of any [*Event Trigger*](../settings/common-input-types/enum/event-trigger.md), the default value is *'OnHotkey'*

* *`ResetGameBlinkRandomizer_EventTrigger`*: Which event will trigger the game's blink randomizer being reset

    * Values can be the name of any [*Event Trigger*](../settings/common-input-types/enum/event-trigger.md), the default value is *'OnHotkey'*

    * Basically, this allows properly re-seeding blinks between runs without having to re-launch the game with the same Session seed

    * If the *active Session seed* is changed, the *blink randomizer* will continue using the *Session* seed it was last reset with until it is reset again

### Menu UI

* *`SkipMainMenuIntro`*: Whether the mod should immediately skip the intro cutscene and title screen upon loading into the *Main Menu*

    * Values can be *'Always'*, *'OnStartup'*, and *'Never'*, the default value is *'Never'*

* *`DisableReturnToMainMenuPopup`*: Whether the mod should disable the *confirmation popup* being displayed when attempting to return to the *Main Menu* from the *Pause Menu*

    * Values can be any [*boolean*](../settings/common-input-types/basic.md#boolean), the default value is *'false'*

* *`DisableCreateSavePopup`*: Whether the mod should disable the *confirmation popup* being displayed when creating a new save using the *Main Menu*

    * Values can be any [*boolean*](../settings/common-input-types/basic.md#boolean), the default value is *'false'*

* *`DisableResetSavePopup`*: Whether the mod should disable the *confirmation popup* being displayed when resetting an existing save using the *Main Menu*

    * Values can be any [*boolean*](../settings/common-input-types/basic.md#boolean), the default value is *'false'*

### Save Files

* *`DisableSaveSelectDelay`*: Whether the mod should disable the small delay before the *scene transition* after selecting a save in the *Main Menu*

    * Values can be any [*boolean*](../settings/common-input-types/basic.md#boolean), the default value is *'false'*

* *`DisableSaveFileLockAfterCompletion`*: Whether the mod should disable save files becoming *locked* after being completed

    * Values can be any [*boolean*](../settings/common-input-types/basic.md#boolean), the default value is *'false'*

* *`DisableFileEncryption_GameSave`*: Whether the mod should prevent the game from *encrypting* game save files when they are updated

    * Values can be any [*boolean*](../settings/common-input-types/basic.md#boolean), the default value is *'false'*

    * When this setting is set to *'true'*, already encrypted save files will be *un-encrypted* the next time they are updated. When set to 'false', *un-encrypted* save files will be *re-encrypted* when they are updated.

    * The game itself does not normally support loading *un-encrypted* save files, so this behaviour is handled by the mod. *Un-encrypted* save files will not be loaded properly without this mod present.

* *`DisableFileEncryption_MetaSave`*: Whether the mod should prevent the game from *encrypting* the *meta* save file when it is updated

    * Values can be any [*boolean*](../settings/common-input-types/basic.md#boolean), the default value is *'false'*

    * Similar to game save files, the *meta* save file will not be properly loaded without this mod present if it is *un-encrypted*. If this happens, the game will erase your meta save data and force you to repeat the cold open after it is launched, which is mildly annoying. To avoid this, just make sure you disable this setting and quickly open/close the game before uninstalling the mod. If you are already in-game, you can disable the setting, reload the config, and close the game for the same effect.

* *`DisableSteamRemoteSaveSync`*: Whether the mod should prevent the game from overwriting existing save files with backups from *Steam Remote Storage* on launch

    * Values can be any [*boolean*](../settings/common-input-types/basic.md#boolean), the default value is *'false'*

    <sub>Note: Even if you have *Steam Cloud* disabled, the game will still regularly write save file updates to a local folder on your device that is managed by *Steam*, referred to as *Remote Storage*. Disabling *Steam Cloud* only prevents the save files in your *Remote Storage* from being backed up on *Steam*'s servers, it will not prevent the game from overwriting your save files with them on launch.</sub>

### Gameplay

* *`GameAutoSavingDisabledByDefault`*: Whether the mod should disable the game's automatic saving feature by default on launch

    * Values can be any [*boolean*](../settings/common-input-types/basic.md#boolean), the default value is *'false'*

        <sub>⚠️ If the game's autosaving feature is forcibly disabled at any point during a speedrun submitted to the <a href="https://www.speedrun.com/dreambbq" target="_blank" rel="noopener noreferrer">*speedrunning leaderboard*</a>, the run will not be verified</sub>