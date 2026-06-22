---
title: Useful Features for Speedrunning
parent: Getting Started
has_children: true
nav_order: 2
---

### Instant Run Resets

Runs can be reset *instantly* by immediately wiping the current save and restarting it from the very beginning, with the same seed, without having to go through the *Main Menu* at all.

To do this, simply press the mod's built-in `ResetSaveWithFileSeed` hotkey while loaded into a save, which is bound to the *F3* key by default.

<br>

### Basic Savestate Manipulation

Using some of the mod's built-in hotkeys to move between areas and mess around with savestates, *seeded Frogger routes* on certain saves can be easily practiced without the fear of having to restart the save. This also allows for much quicker resets between attempts when practicing certain skips, such as *"Purple Guy"*.

* For more info, see [Basic Savestate Manipulation](basic-savestate-manipulation.md)

<br>

### Automatic Run Seeding

Runs can be automatically seeded by changing how and when the game generates certain seed types, allowing runners to seed certain parts of runs that were previously unseedable.

* For more info, see [Automatic Run Seeding](automatic-run-seeding.md)

<br>

### Simulated Achievement Notifications

All runs submitted to the game's <a href="https://www.speedrun.com/dreambbq" target="_blank" rel="noopener noreferrer">*speedrunning leaderboard*</a> in the *All Achievements* category can be verified by using this mod's *Simulated Achievement notifications* to keep track of a run's completed achievements, as an alternative to relying on the *Steam Overlay's achievement popups*, which are notoriously slow and tedious to setup between runs.

The way this feature works is simple, every time you *would have* triggered an *achievement* popup through *Steam*, the mod will add the *achievement* to the current save's own seperate list of *achievements*, which will be stored and retrieved from it's *save file* just like vanilla save data.

When the `NotifyOnSimulatedAchievements` config setting is set to *'true'*, the mod will show a *notification* on your screen every time a unique *achievement* is added to the current save's *simulated achievements list*, displaying both the name of the *achievement* and the number of *achievements* the save has in it's list.