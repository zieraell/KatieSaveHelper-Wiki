---
title: How to Install
parent: Getting Started
nav_order: 1
---

There are two supported mod loaders, follow the instructions for the one you would like to use.

### [BepInEx](https://github.com/BepInEx/BepInEx/releases/latest)

Drag the **BepInEx** version of the latest mod `.dll` file into the `BepInEx/plugins` folder

In the `BepInEx/config` folder, find and open your `BepInEx.cfg` file, and make sure the *`HideManagerGameObject`* setting under the `[Chainloader]` section is set to ***'true'***. *This is required for the mod to work properly.*

I also highly reccomend enabling the *logging console* for more real time feedback from the mod. This can be done by changing the *`Enabled`* setting under the `[Logging.Console]` section to ***'true'***.

In the same folder, you can edit the `Zieraell.KatieSaveHelper.cfg` file to configure the mod after launching the game once.

### [MelonLoader](https://github.com/LavaGang/MelonLoader/releases/latest)

Drag the **MelonLoader** version of the latest mod `.dll` file into the `Mods` folder

To configure the mod, find and edit the `[KatieSaveHelper]` section in your `UserData/MelonPreferences.cfg` file after launching the game once.