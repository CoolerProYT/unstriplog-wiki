# Common Config
Common config allows us to modify the basic features of the mod.

## Config Options
| Field             | Type    | Default           | Description                                                                          |
|-------------------|---------|-------------------|--------------------------------------------------------------------------------------|
| `item`            | String  | `unstriplog:bark` | Id of the item to use as drop when stripping log, and use as item to unstrip log.    |
| `allowUnknownLog` | Boolean | `true`            | Allow logs that have no drop item defined to use the item above and unstrip with it. |

::: info
To set a unique drop/item to unstrip, please visit [Unstrip Detailed Config](/unstrip-detailed-config).
:::

## Config File
The common config file can be found under `config/unstriplog-common.toml`. Below is an example of what the config file will look like:

::: code-group
```toml [unstriplog-common.toml]
item = "unstriplog:bark"
allowUnknownLog = true
```
:::