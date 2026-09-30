---
title: Custom Save Data
parent: Modding API
has_children: true
nav_order: 2
---

Extra fields can easily be added to existing objects of any class type by using the mod's *Custom Data* system.

⚠️ ***Please note that this feature is currently unfinished and subject to changes in future updates*** ⚠️


### Assigning and Managing Custom Data

First, a class must be created as a container template for the extra data:

```cs
public class ExampleExtraData
{
    public int Points = 0;
    public string Text = "";
}
```

Then, a data container type can be attached to any object using one of the mod's extension methods for the `object` type:

```cs
var sceneChanger = new SceneChanger();

ExampleExtraData extraData = sceneChanger.GetOrCreateCustomData<ExampleExtraData>();
```

The `GetOrCreateCustomData<T>()` method will associate a new instance of a data container type with the target object, assuming a data container instance of the same type is not already associated with the object.

The method will also return the new or existing instance of the specified data container type associated with the object, which can used to read or edit the object's extra data.

```cs
extraData.Points += 1;

if (extraData.Points >= 10)
  extraData.Text = "10 points!";
```

To check if an object has any custom data containers associated with it, the `HasCustomData()` method can be used. The `HasCustomData<T>()` method can also be used to check if an object is associated with a custom data container of a certain type.

To remove a specific custom data container from an object:
```cs
Dictionary<Type, object> objDataDict = sceneChanger.GetCustomDataContainer().Data;

objDataDict.Remove(typeof(ExampleExtraData));
```
Or to remove all custom data containers:
```cs
objDataDict.Clear();
```


<sub>(A helper method for removing custom data will be added in a future update)</sub>

### Custom Save Data

When *custom data containers* that use the `CustomSaveData` *type attribute* are attached to object types that end up being serialized to save files, the mod will serialize the container's data to the file as well.

When these save files are deserialized and converted to a *file data* object that contains the save data, any *custom data* the save file contained will be deserialized into *custom data container* objects, and automatically attached to the *file data* object.

Here is a simple example of a *custom data container* class used within the mod itself to store per-save achievements:
```cs
[CustomSaveData("genericData")]
public class KatieSaveData
{
    public List<string> achievementList = new List<string>();
}
```

The `CustomSaveData` class attribute takes one string argument that represents the *identifier* of the *custom data container* type. This will be used as the name for the container type when it is serialized to a save file, and to link the *container identifier* back to an actual *custom data container* type when a save file is being deserialized.

Here is what this example class looks like when it is serialized:

```json
"__moddedData": {
  "KatieSaveHelper": {
    "genericData": {
      "achievementList": [
          "ACH_ENA_BLINK"
      ]
    }
  }
}
```

Each entry stored under *"__moddedData"* is a *mod identifier*, and each entry stored under a *mod identifier* is a separate instance of a *custom data container*, which includes it's *identifier* and relevant data. A container type's *mod identifier* is currently derived from the *mod name* specified in the assembly it is defined in, but this may be changed in a future update.

For *BepInEx* mods, the mod name is specified in `BepInPlugin` attribute used on the *main* class.

For *MelonLoader* mods, the mod name is specified in the `MelonInfo` assembly attribute.

### Game File Data Types

Regular Save files allow storing per-save custom data. They are  serialized from and deserialized to the `SaveFileData` type.

You can obtain the instance of this type from the current save with:

```cs
JoelG.ENA4.SaveFile.CurrentSave
```

<br>

The *Meta* Save file allows storing custom data that persists between saves and across all game sessions. It's relevant type is `MetaSaveFileData`.

The currently loaded instance of this type can be obtained with:

```cs
JoelG.ENA4.MetaSaveFile.Current
```

<br>

The *Preferences* Save file has the same custom data storage behavior as *Meta* Save files, except it's data is stored in the game's `preferences.json` file, making it more suited for storing data related to mod configuration via GUI. It's relevant type is `PreferencesData`.

The currently loaded instance of this type can be obtained with:

```cs
JoelG.ENA4.Preferences.Current
```


