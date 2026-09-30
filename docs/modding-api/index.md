---
title: Modding API
has_children: true
nav_exclude: true
nav_order: 4
---

If you would like to make your own mod for **ENA: Dream BBQ** that uses a *modloader*, this mod exposes a few features that you might find useful.

If you are building your mod using *Visual Studio* or *Rider*, you must add this mod's latest `.dll` file to your project as a *Reference*. See [this github page](github.com/ENA-Speedrunning-Tools/Katie-Save-Helper/releases/latest) for the file download.

Afterwards, you must use the mod's API namespace in any class files where it will be used. This can be done with:

```cs
using KatieSaveHelper.Features.API;
```

Finally, after building your mod, it must be installed along with the same `.dll` file that was used as a *Reference* in your project.

