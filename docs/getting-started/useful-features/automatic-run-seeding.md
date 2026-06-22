---
title: Automatic Run Seeding
parent: Useful Features for Speedrunning
nav_order: 2
---

<br>

To change *how* certain seeds are generated, each ***seed type*** can be configured to use a specific [*Seed Generator*](../../settings/common-input-types/enum/seed-generator.md) by changing it's `Generator_Type` config setting.

By default, the mod uses the game's built-in seed generators for each *seed type* to mimick normal gameplay. However, the mod also includes two *custom* generators specifically for seeding runs:

* **Static**: Always produces a seed matching the value of the seed type's corresponding `Generator_StaticSeedValue` config setting.

* **PseudoRandom**: Similar to the game's built-in *Random* generator, but ensures the randomly produced seed will cause certain in-game events to occur in a specific way.

<br>

Internally, the game uses three different types of seeds to determine randomness for certain events:

### Save Seeds

These are randomly generated every time you start a new save using the in-game Main Menu, and then stored in it's respective save file. Every time you load a save, the game switches to using that save's stored seed as the *active Save seed*.

Things *Save seeds* determine include:

* Which *Taxi Driver Head* you can speak with

* The goal directions and dog obstacles in the *Purge Event*

* The starting positions of the rafts in the *Core*

* Whether one door or multiple in the *Lost Village* can be knocked on

* The starting positions of the *Core* river's rafts after loading into it's area

<br>

Using the *PseudoRandom* generator for *Save* seeds is extremely useful if you are interested in helping the speedrun community search for *Save* seeds that are already optimal, but have a better *raft* layout in the *Core River*. The default *PseudoRandomizer* settings for this seed type already account for the current meta, so further configuration should not be needed, unless you would like to filter out certain obstacles from the *Purge Event* or ensure the *Lost Village* has multiple knockable doors for *All Achievement* runs.

### Session Seeds

These are randomly generated once every time you launch the game, and are mainly used to determine when the player will blink. This is only relevant when running the *All Achievements* category, where the achievement you get for your first blink is required to complete the run.

The easiest method of seeding blinks is to have *Session* seeds use the *PseudoRandom* generator. By default, the *PseudoRandomizer* settings for this seed type will force a blink at the earliest possible window, which is the first time you spend at least 30 seconds in a scene.

<sub>Note: If you are making this change with the game open and would like it to take effect immediately instead of having to restart the game first, you can change the *`SeedType_Session_RegenerateSeed_EventTrigger`* config setting to *'OnLoadSave'*, then load a save.</sub>

However, if only the *Session* seed generator is changed for blink seeding, the game will have to be re-launched after every run to properly re-seed blinks. To avoid this, you can change the *`ResetGameBlinkRandomizer_EventTrigger`* config setting to *'OnLoadSave'*, so blinks will be re-seeded every time you load a save.

### Hardware Seeds

Like *Session seeds*, these are generated once every time you launch the game, but the value is based on the device you are playing on, instead of being random.

There are only a select few random events in-game that are determined with the *Hardware* seed, the only one relevant for speedruns being whether ENA's *Salesman* or *Meanie* side speaks the first line of dialogue when talking to the *Taxi Driver* for the first time. When doing speedruns that go through the *Purge Event*, it is widely accepted in the speedrun community that *Meanie's* line of dialogue is very slightly faster.

If Meanie's dialogue does not play for this event on your device, and you would like to change it, simply change the *Hardware* seed generator to *PseudoRandom*. The *PseudoRandomizer* settings for this seed type set the event to use Meanie's dialogue by default.

<sub>Note: If you are making this change with the game open and would like it to take effect immediately instead of having to restart the game first, you can change the *`SeedType_Hardware_RegenerateSeed_EventTrigger`* config setting to *'OnLoadSave'*, then load a save.