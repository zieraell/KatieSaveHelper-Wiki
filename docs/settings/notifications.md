---
title: Notifications
parent: Settings
nav_order: 5
---

Options to modify the on-screen *toast notifications* that are triggered by certain mod *hotkey* actions

<br>

### General

* *`ShowToastNotifcations`*: Whether the mod should display toast notifications

    * Values can be any [*boolean*](../settings/common-input-types/basic.md#boolean), the default value is *'true'*

* *`SubscribeToAssetUpdates`*: Whether the mod should automatically install certain assets and fonts from this repo's `assets` branch

    * Values can be any [*boolean*](../settings/common-input-types/basic.md#boolean), the default value is *'false'*

    * The first time you launch the game after installing the mod, a confirmation popup will appear in the Main Menu prompting if you would like to subscribe to asset updates. This will not be shown again, even if the mod is re-installed.
    
        * Accepting the popup will automatically set your `SubscribeToAssetUpdates` config setting to *'true'* and begin downloading assets (if they are available)

### Optional Event Notifications

* *`NotifyOnFirstBlinkAttempts`*: Whether the mod should show display a *toast notification* when the game makes an *internal blink attempt* and the *blink randomizer* hasn't triggered a blink yet on it's *current reset*

    * Values can be any [*boolean*](../settings/common-input-types/basic.md#boolean), the default value is *'false'*

* *`NotifyOnSimulatedAchievements`*: Whether the mod should display a *toast notification* when the game ***internally triggers an achievement*** that isn't already in the mod's *Simulated Achievements* list

    * Values can be any [*boolean*](../settings/common-input-types/basic.md#boolean), the default value is *'false'*

* *`ResetSimulatedAchievements_EventTrigger`*: Which event will trigger the mod's internal *Simulated Achievements* list being reset

    * Values can be the name of any [*Event Trigger*](../settings/common-input-types/enum/event-trigger.md), the default value is *'OnHotkey'*


### Appearance

* `Toast_FontFileName`: The file name (without the extension) of a `.ttf` file inside the `Zieraell.KatieSaveHelper/Fonts` folder (which is in the same directory as the mod `.dll` file), that the mod will attempt to load as the font style for toasts

    * If a `.ttf` file with the name configured in this setting does not exist in the `/Fonts` folder, the mod will default to using the game's *built-in* font for toasts. This built-in font unfortunately **does not support font outlines**.

    * The default value is *'RuneScape-ENA'*, which is a *perfect replica* of the game's *built-in* font, **created by *@Birbkeks***. However, this file will not exist in the `/Fonts` folder initially. It can be installed by either [*subscribing to asset updates*](#general) or downloading it to the `/Fonts` folder manually from the [`assets`](https://github.com/ENA-Speedrunning-Tools/Katie-Save-Helper/blob/assets/Fonts) branch of the mod's [github repo](https://github.com/ENA-Speedrunning-Tools/Katie-Save-Helper).

* `Toast_FontSize`: The font size toasts should use

    * Values can be any [*integer*](../settings/common-input-types/basic.md#integer) above *0*, the default value is *'36'*

* `Toast_FontColor`: The font color toasts should use

    * Values can be any [*hex code*](../settings/common-input-types/basic.md#hex-code), the default color value is *white*, or *'#FFFFFF'*

* `Toast_ScreenPosition`: Where on the screen the toast should be positioned

    * Values can be :

        * *'TopLeft'*, *'Top'*, *'TopRight'*

        * *'CenterLeft'*, *'Center'*, *'CenterRight'*

            * If you would like the toast to be positioned in the center of the screen, but slightly above the cursor, you can use *'Baseline'*

        * *'BottomLeft'*, *'Bottom'*, *'BottomRight'*

    * The default value is *'TopRight'*

* *`Toast_OutlineWidth`*: The percentage of the maximum font width the toast should use

    * Values can be any [*integer*](../settings/common-input-types/basic.md#integer) between 0 and 100, the default value is *'5'*

    * Setting the value to *'0'* will not render any outline on the toast

* *`Toast_OutlineColor`*: The font outline color the toast should use

    * Values can be any [*hex code*](../settings/common-input-types/basic.md#hex-code), the default color value is *black*, or *'#000000'*

* *`Toast_Opacity`*: The opacity of the text the toast should use

    * Values can be any [*integer*](../settings/common-input-types/basic.md#integer) between *0* and *100*, the default value is *'100'*

    * Setting the value to *'0'* will make the text fully transparent

### Timings

* *`Toast_FadeInTime`*: The amount of time it takes for the toast to fade-in (in seconds)

    * Values can be any [*float*](../settings/common-input-types/basic.md#float) 0 or above, the default value is *'0.25'*

* *`Toast_FadeOutTime`*: The amount of time it takes for the toast to fade-out (in seconds)

    * Values can be any [*float*](../settings/common-input-types/basic.md#float) 0 or above, the default value is *'0.25'*

* *`Toast_HoldTime`*: The amount of time the toast will remain on the screen after fully fading-in before starting to fade-out (in seconds)

    * Values can be any [*float*](../settings/common-input-types/basic.md#float) 0 or above, the default value is *'1.50'*

* *`SimulatedAchievementToast_HoldTime`*: How long *Simulated Achievement* toasts should remain on the screen before starting to fade out

    * Values can be any [*float*](../settings/common-input-types/basic.md#float) 0 or above, the default value is *'5.0'*

* *`Toast_GapTime`*: The amount of time to wait after a toast fully fades out before displaying another toast (in seconds)

    * Values can be any [*float*](../settings/common-input-types/basic.md#float) 0 or above, the default value is *'0.25'*