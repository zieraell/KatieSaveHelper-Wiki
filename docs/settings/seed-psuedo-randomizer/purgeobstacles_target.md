---
title: PurgeObstacles_Target
parent: Seed Pseudo-Randomizer
nav_order: 2
---

<br>

* Each entry, separated by commas, represents a ***condition*** that a specific generated room in the *Purge Event* **must pass** for a given seed to be considered *valid* by the *pseudo-randomizer*.

* When an entry contains the *name* of an *obstacle*, or a *sub-list* of obstacle names, this represents a **'must be'** condition.

    * <span class="example">For example, if the entry was <em>'FishChain'</em>, the specific generated room <strong>must</strong> contain the <em>FishChain</em> obstacle.</span>

    * <span class="example">If the entry was <em>'[FishChain, FishStomp]'</em>, the specific generated room <strong>must</strong> contain <strong>either</strong> the <em>FishChain</em> <strong>or</strong> <em>FishStomp</em> obstacles.</span>

* When an entry with an obstacle name or sub-list of obstacle names is prefixed with the **'!'** symbol, this converts the entry into a **'must not be'** condition.

    * <span class="example">For example, if the entry was <em>'!WanderingFish'</em>, the specific generated room <strong>must not</strong> contain the <em>WanderingFish</em> obstacle.</span>

    * <span class="example">If the entry was <em>'![WanderingFish, ManyFishFlipped]'</em>, the specified generated room <strong>must not</strong> contain <strong>either</strong> the <em>WanderingFish</em> <strong>or</strong> <em>ManyFishFlipped</em> obstacles.</span>

* Finally, when an entry is simply the word *'Any'*, this represents an **'any'** condition, which doesn't perform any obstacle checks on the specific generated room.

<br>

* By default, **each set of three entries** represents a condition for the rooms immediately to the **left, forward, and right** of each generated room, respectively.

    * <span class="example">For example, setting <code>PurgeObstacles_Target</code> to <em>'FishStruggle, FishStruggle, FishStruggle'</em> will have the <em>pseudo-randomizer</em> search for seeds where <strong>every door</strong> from the <strong>spawn room</strong> in the Purge Event will lead to a room with the <em>FishStruggle</em> obstacle.</span>

    * <span class="example">Setting <code>PurgeObstacles_Target</code> to <em>'Any, Any, Any, FishChain, FishChain, FishChain'</em> will have the <em>pseudo-randomizer</em> search for seeds where <strong>every door</strong> from the <strong>second room you walk in</strong> will lead to a room with the <em>FishChain</em> obstacle.</span>

* The list can have as many **sets of three** condition entries as you like, but as the list grows longer and more specific, it will become ***exponentially*** harder for the *pseudo-randomizer* to find a valid seed.

### Shorthand Formats

* When a **'\*'** symbol is placed at the start of the setting input, the list converts to using a more **shorthand format**, where each entry only represents a condition for the desired obstacle in the **goal direction** for each room, specified in `PurgeGoals_Target`.

    * <span class="example">For example, <em>'Any, FishStruggle, Any'</em> could be shortened to <em>'*FishStruggle'</em>, because the first <strong>goal direction</strong> is always <strong>forward</strong>, regardless of seed.</span>

* Assuming `PurgeGoals_Target` was set to the default value (*'\*RLRLRL'*), *'\*SneakAttack, !WanderingFish'* would be the **shorthand** version of *'Any, SneakAttack, Any, Any, Any, !WanderingFish'*, making sure the **first** generated room has a room **with** the *SneakAttack* obstacle past it's **forward** door, and that the **second** generated room has a room **without** the *WanderingFish* obstacle past it's **right** door.

* Since this **shorthand** format assumes you will **only** be generating rooms past the entrances in each **goal direction**, the list only takes **up to five** entries, as the game will stop generating room obstacles when you have **two or less** goals left. So, the specific direction for each entry using this format will always be *'Forward'* plus the **first four** directions listed in your current `PurgeGoals_Target` config setting. In the case of using the default value (again, *'\*RLRLRL'*), these would be *'Right', 'Left', 'Right', 'Left'*.

* When **two** **'\*'** symbols are placed at the start of the setting input, the list converts to using a **more concise** version of the **shorthand format**, taking only two entries. The first represents the obstacle condition for the room towards the first goal direction, which is always forward. The second represent the obstacle condition in the rooms towards the next four goal directions.

    * <span class="example">For example, <em>'**Any, !WanderingFish'</em> is just a shorter version of <em>'*Any, !WanderingFish, !WanderingFish, !WanderingFish, !WanderingFish'</em>.</span>

* When **three** **'\*'** symbols are placed at the start of the setting input, the list converts to using the **most concise** version of the **shorthand format**, only taking **one entry** that represents the obstacle condition for each room past the first five goal directions.

    * <span class="example">For example, <em>'***FishBar'</em> is just a shorter version of <em>'**FishBar, FishBar'</em>.</span>

<br>

### List of Purge Obstacles

<br>

**FishBar**

<figure>
    <img src="{{ site.baseurl }}/assets/images/purge-obstacles/FishBar.JPG" width="400">
</figure>

<br>

**FishChain**

<figure>
    <img src="{{ site.baseurl }}/assets/images/purge-obstacles/FishChain.JPG" width="400">
</figure>

<br>

**FishChomp**

<figure>
    <img src="{{ site.baseurl }}/assets/images/purge-obstacles/FishChomp.JPG" width="400">
</figure>

<br>

**FishStruggle**

<figure>
    <img src="{{ site.baseurl }}/assets/images/purge-obstacles/FishStruggle.JPG" width="400">
</figure>

<br>

**FishThrash**

<figure>
    <img src="{{ site.baseurl }}/assets/images/purge-obstacles/FishThrash.JPG" width="400">
</figure>

<br>

**ManyFishFlipped**

<figure>
    <img src="{{ site.baseurl }}/assets/images/purge-obstacles/ManyFishFlipped.JPG" width="400">
</figure>

<br>

**SneakAttack**

<figure>
    <img src="{{ site.baseurl }}/assets/images/purge-obstacles/SneakAttack.JPG" width="400">
</figure>

* If this obstacle is selected for a room that is adjacent to the spawn room, it will not be spawned, and the room will be empty

<br>

**WanderingFish**

<figure>
    <img src="{{ site.baseurl }}/assets/images/purge-obstacles/WanderingFish.JPG" width="400">
</figure>

* If this obstacle is selected for a room that is adjacent to the spawn room, it will not be spawned, and the room will be empty

* When this obstacle is generated, it will fly out of it's room through the entrance, then continue flying in the same direction into the next room before being despawned