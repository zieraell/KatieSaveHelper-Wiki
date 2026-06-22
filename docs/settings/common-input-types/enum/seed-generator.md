---
title: Seed Generator
parent: Enum
nav_order: 2
---

An enum used by settings that modify how certain *seed types* will generate seed values.

<br>

* ***Random***: A built-in generator that produces a completely random seed every time.

* ***Device***: A built-in generator that produces a seed based on your hardware information (your default hardware seed). The produced seed will be the same every time as long as the game is launched on the same device.

* ***Static***: A modded generator that always produces a seed matching the value of the seed type's corresponding `StaticSeed` config setting.

* ***PseudoRandom***: A modded generator that is similar to the game's built-in *Random* generator, but ensures the randomly produced seed will cause certain in-game events to occur in a specific way.