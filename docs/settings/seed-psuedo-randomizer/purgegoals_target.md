---
title: PurgeGoals_Target
parent: Seed Pseudo-Randomizer
nav_order: 1
---

<br>

* By default, this setting takes a list of **up to six** goal directions, separated by commas. (ex. *'Right, Left, Right, Left, Right, Left'*)

* Placing a **'\*'** symbol at the start of the setting enables a *shorthand format* where **each character** represents a goal direction. (ex. *'\*RLRLRL'*)

* Valid directions are *'Right'* / *'R'*, *'Left'* / *'L'*, *'Forward'* / *'F'*, and *'Any'* / *'A'*.

* A direction is invalid if it matches the direction immediately before it. (unless the previous direction is *'Any'*)

    * <span class="example">For example, the first goal direction is always <em>'Forward'</em>, regardless of seed, so the first direction listed in the setting must be either <em>'Right'</em>, <em>'Left'</em>, or <em>'Any'</em>.</span>

    * Any invalid directions will be internally replaced with *'Any'* before the mod starts generating a *pseudo-random* seed.