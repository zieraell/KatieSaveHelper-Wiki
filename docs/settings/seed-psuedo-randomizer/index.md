---
title: Seed Pseudo-Randomizer
parent: Settings
nav_order: 3
---

Options to configure the mod's *seed pseudo-randomizer* feature, which allows generating and loading random seeds that would trigger specific in-game events

<br>

## Targetable Events

Below are the various events the mod's *pseudo-randomizer* will target when generating a new seed

### Save Seed Mode

* *`FrankDoor_Target`*: Which doors in the lost village will be knockable

    * Values can be *'Single'*, *'Multiple'*, or *'Any'*, the default value is *'Any'*

* *`TaxiHead_Target`*: The name of the head that will be interactable when talking to the Taxi Driver

    * Values can be *'Creisi'* (blue head), *'Doom'* (grey head), *'Socio'* (human head), and 'Any', the default value is *'Socio'*

* *`PurgeGoals_Target`*: The order of the room goals during the Purge Event Maze

    * The default value is *'\*RLRLRL'*

    * For more info about this setting, see [PurgeGoals_Target](purgegoals_target.md)


* *`PurgeObstacles_Target`*: The dog obstacles within each generated room during the Purge Event Maze

    * The default value is *'**Any, !WanderingFish'*

    * For more info about this setting, see [PurgeObstacles_Target](purgeobstacles_target.md)

### Session Seed Mode

* *`FirstBlinkAttempt_Target`*: The range of internal blink attempts that will trigger the player's first blink

    * Input formats: 

        * '#' (where the *#* symbol is any [*integer*](../settings/common-input-types/basic.md#integer)), the player's first blink must be at this **exact** attempt number

        * '..#', the player's first blink must be at this **exact** attempt number **or lower**

        * '#..', the player's first blink must be at this **exact** attempt attempt number **or higher**

        * '#..#', the player's first blink must be **between** these two **exact** attempt numbers

    * The default value is *'1'*

* `FirstBlinkAttempt_AssumeInCore`: Whether to assume the player has the increased *blink chance* when in the *Core* area as it is trying to find a matching seed

    * The default value is *'false'*

    * Note that any *Session* seed found with this setting set to *'false'* will still have you blink within the attempt number range specified in the `FirstBlinkAttempt_Target` config setting when in the *Core* area

### Hardware Seed Mode

* *`EnaTaxiMood_Target`*: Which side of ENA will talk during the second dialogue line of the first Taxi Driver interaction

    * Values can be *'Meanie'* or *'Salesman'*, the default value is *'Meanie'*

### General Settings

* *`NaturalSeedsOnly`*: Whether the mod's pseudo-randomizer should exclusively generate seeds the game itself can naturally generate

    * Values can be any [*boolean*](../settings/common-input-types/basic.md#boolean), the default value is *'true'*

    * When set to *'true'*, only positive seed values can be generated. When set to *'false'*, both positive and negative seed values can be generated, effectively **doubling** the number of possible seeds.

* *`SearchAttemptLimit`*: The maximum number of attempts the *pseudo-randomizer* will make to find a matching seed before quitting

    * Values can be any [*integer*](../settings/common-input-types/basic.md#integer), the default value is *'1000000'*

    * When the *pseudo-randomizer* quits due to reaching it's configured *search attempt limit*, it will in some cases default to using the vanilla *Random* generator to produce a seed.