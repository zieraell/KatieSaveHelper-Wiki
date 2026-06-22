---
title: Event Trigger
parent: Enum
nav_order: 3
---

An enum used by settings that *execute an action* whenever a certain *event* is triggered. These settings typically have the `<Action>_EventTrigger` name format.

<br>

* ***OnLoadSave***: Triggers upon loading into any save from the *Main Menu* or using one of the `ReloadSave` or `ResetSave` hotkeys.

* ***OnCreateSave***: Triggers upon creating a new save from the *Main Menu* or using one of the `ResetSave` hotkeys.

* ***OnLoadMainMenu***: Triggers upon loading into the *Main Menu*.

* ***OnHotkey***: Triggers whenever the action's relevant *hotkey* is pressed.

    * Every `<Action>_EventTrigger` config setting will have an associated `<Action>_Key` setting, where the *hotkey* that triggers the *OnHotkey* event for it's specific *action* can be bound.

    * If an `<Action>_EventTrigger` setting is not set to *'OnHotkey'*, that action's associated *hotkey* will be *disabled*.