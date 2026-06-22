---
title: Scene Transitions
parent: Hotkeys
nav_order: 2
---

Options to modify the *scene transitions* for each of the mod's *hotkey actions* that trigger a *scene change*

<br>

* *`HotkeySceneTransition_Type`*: The transition type to use for the *scene change*

    * Values can be *'Immediate'* and *'FadeToColor'*, the default value is always *'FadeToColor'*

<br>

The following options will not impact the respective transition if it's type is set to *'Immediate'*:

* *`HotkeySceneTransition_Color`*: The color that the *scene transition* will fade into and out of

    * Values can be any [*hex code*](../settings/common-input-types/basic.md#hex-code), the default color value is always *black*, or *'#000000'*

* *`HotkeySceneTransition_FadeInTime`*: The duration of the fade-in effect of the *scene transition* (in seconds)
    * Values can be any [*float*](../common-input-types/basic.md#float), the default value is always *'0.5'*
    
* *`HotkeySceneTransition_FadeOutTime`*: The duration of the fade-out effect of the *scene transition* (in seconds)
    * Values can be any [*float*](../common-input-types/basic.md#float), the default value is always *'0.5'*