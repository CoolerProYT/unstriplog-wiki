# Common Config
Common config allows us to modify basic feature of the mod.

## Config Options
| Field             | Type    | Default           | Description                                                                                      |
|-------------------|---------|-------------------|--------------------------------------------------------------------------------------------------|
| `item`            | String  | `unstriplog:bark` | Id of the item to use as drop when stripping log, and use as item to unstrip log.                |
| `allowUnknownLog` | Boolean | `true`            | Allow log that has no drop item defined to drop item defined in above field and unstrip with it. |

::: info
To set unique drop/item to unstrip please visit [Unstrip Detailed Config](/unstrip-detailed).
:::

## Config File
The common config file can be found under `config/unstriplog-common.toml`. Below will include an example of what the config file will look like:

::: code-group
```toml [unstriplog-common.toml]
item = "unstriplog:bark"
allowUnknownLog = true
```
:::