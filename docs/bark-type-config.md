# Bark Type Config
Bark Type Config allows us to add different type of bark to the mod. By default, bark type for every vanilla wood/log has been added.

## Config Options
It is a JSON config, this config file store an array of BarkTypeEntry.

### BarkTypeEntry

| Field     | Type                 | Example                                 | Description                                                                                                |
|-----------|----------------------|-----------------------------------------|------------------------------------------------------------------------------------------------------------|
| `name`    | String               | `oak`                                   | The name of the bark, must be unique. Translation need to be added to `en_us.json`, will be covered later. |
| `texture` | String               | `unstriplog:textures/item/oak_bark.png` | Texture location of the bark type.                                                                         |

### Adding Translation Key
Click [here](https://minecraft.wiki/w/Resource_pack#Language) to see minecraft wiki for adding language to resource pack.

The translation key has to start with `item.unstriplog.` following by bark type name and `_bark`.

Example:
::: code-group
```json5 [en_us.json]
{
  "item.unstriplog.oak_bark": "Oak Bark"
}
```
:::

### Adding Texture
The texture must be located in the namespace and path defined in `texture` field of the bark type. Because the rendering of bark item are hardcoded, it will always render as `item/generated`.

## Config File
The config file can be found under `config/unstriplog/bark-type.json`. Below will include an full example of what the config file will look like:

::: code-group
```json5 [unstriplog/bark-type.json]
[
  {
    "name": "cherry",
    "texture": "unstriplog:textures/item/cherry_bark.png"
  },
  {
    "name": "mangrove",
    "texture": "unstriplog:textures/item/mangrove_bark.png"
  },
  {
    "name": "spruce",
    "texture": "unstriplog:textures/item/spruce_bark.png"
  },
  {
    "name": "birch",
    "texture": "unstriplog:textures/item/birch_bark.png"
  },
  {
    "name": "pale_oak",
    "texture": "unstriplog:textures/item/pale_oak_bark.png"
  },
  {
    "name": "jungle",
    "texture": "unstriplog:textures/item/jungle_bark.png"
  },
  {
    "name": "dark_oak",
    "texture": "unstriplog:textures/item/dark_oak_bark.png"
  },
  {
    "name": "warped",
    "texture": "unstriplog:textures/item/warped_bark.png"
  },
  {
    "name": "oak",
    "texture": "unstriplog:textures/item/oak_bark.png"
  },
  {
    "name": "acacia",
    "texture": "unstriplog:textures/item/acacia_bark.png"
  },
  {
    "name": "bamboo",
    "texture": "unstriplog:textures/item/bamboo_bark.png"
  },
  {
    "name": "crimson",
    "texture": "unstriplog:textures/item/crimson_bark.png"
  }
]
```
:::