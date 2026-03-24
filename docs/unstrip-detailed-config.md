# Unstrip Detailed Config
Unstrip Detailed Config allows us to define drop and unstrip item for each set of normal and stripped wood/log.

## Config Options
It is a JSON config, this config file store an array of LogEntry.

### LogEntry

| Field          | Type                 | Example                                | Description                                                                                                                                      |
|----------------|----------------------|----------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------|
| `base`         | String               | `minecraft:oak_log`                    | Id of the log/wood that you want to define custom drop and unstrip item.                                                                         |
| `stripped`     | String               | `minecraft:stripped_oak_log`           | Id of the stripped log/wood that is the stripped version of the defined log/wood in `base`.                                                      |
| `drop`         | ItemEntry            | Please look at ItemEntry Section below | Item id and DataComponents Json Object of the item to use as drop when stripping.                                                                |
| `unstrip_item` | ItemEntry (Optional) | Please look at ItemEntry Section below | Item id and DataComponents Json Object of the item to use as unstrip item when unstripping, if not defined, `drop` will be used as unstrip item. |

A simple example of LogEntry:
```json5
[
  {
    "base": "minecraft:jungle_wood",
    "stripped": "minecraft:stripped_jungle_wood",
    // "drop": {}, // Will be shown in ItemEntry Section
    // "unstrip_item": {}, // Optional
  }
]
```

### ItemEntry

| Field        | Type                          | Example                                         | Description                                                                           |
|--------------|-------------------------------|-------------------------------------------------|---------------------------------------------------------------------------------------|
| `id`         | String                        | `unstriplog:bark`                               | Id of the item that you want to use as the drop/unstrip_item when stripping log/wood. |
| `components` | DataComponentPatch (Optional) | Please look at DataComponentPatch Section below | A map of data component types and value that the item should have.                    |

### DataComponentPatch
DataComponent is a vanilla thing, you can find all vanilla components and their fields [here](https://minecraft.wiki/w/Data_component_format#List_of_components).

| Field                                                       | Type        | Example                                                                          | Description                                         |
|-------------------------------------------------------------|-------------|----------------------------------------------------------------------------------|-----------------------------------------------------|
| Any valid data component type id eg. `unstriplog:bark_type` | Json Object | The field in the component type Json Object are according to the component type. | Valid components that the defined item should have. |

::: warning
If the item with components are using as unstrip item, all components must strictly match otherwise it will not work!
:::

A simple example of ItemEntry and DataComponentPatch:
```json5
[
  {
    // "base": "minecraft:jungle_wood",
    // "stripped": "minecraft:stripped_jungle_wood",
    "drop": {
      "id": "unstriplog:bark",
      "components": { // This is an optional field.
        "unstriplog:bark_type": { // This is the id of the registered DataComponentType
          "name": "jungle", // This is one of the field in `unstriplog:bark_type`
          "texture": "unstriplog:textures/item/jungle_bark.png", // This is also one of the field in `unstriplog:bark_type`
        }
      }
    },
    "unstrip_item": { // Optional
      "id": "minecraft:paper",
      // No "components" field is needed because it is optional
    }
  }
]
```

## Config File
The config file can be found under `config/unstriplog/unstrip-detailed.json`. Below will include an full example of what the config file will look like:

::: code-group
```json5 [unstriplog/unstrip-detailed.json]
[
  {
    "base": "minecraft:jungle_wood",
    "stripped": "minecraft:stripped_jungle_wood",
    "drop": {
      "id": "unstriplog:bark",
      "components": {
        "unstriplog:bark_type": {
          "name": "jungle",
          "texture": "unstriplog:textures/item/jungle_bark.png"
        }
      }
    }
  },
  {
    "base": "minecraft:cherry_log",
    "stripped": "minecraft:stripped_cherry_log",
    "drop": {
      "id": "unstriplog:bark",
      "components": {
        "unstriplog:bark_type": {
          "name": "cherry",
          "texture": "unstriplog:textures/item/cherry_bark.png"
        }
      }
    }
  },
  // Other vanilla log/wood
]
```
:::