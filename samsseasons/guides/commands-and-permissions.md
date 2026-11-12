---
description: Reference for all SamsSeasons commands!
icon: rectangle-terminal
---

# Commands & Permissions

## Commands & Permissions

Every command starts with `/seasons` (aliases: `/samsseasons`, `/season`).

***

### Player Commands

| Command                                            | Description                                       | Permission                                           | Default                 |
| -------------------------------------------------- | ------------------------------------------------- | ---------------------------------------------------- | ----------------------- |
| `/seasons`                                         | Open the season overview                          | `samsseasons.menu`                                   | everyone                |
| `/calendar` (or `/seasons calendar`)               | Open the season calendar                          | `samsseasons.calendar`                               | everyone                |
| `/seasons info [world]`                            | The current season, phase, date and progress      | `samsseasons.info`                                   | everyone                |
| `/seasons forecast [world]`                        | Weather for the coming days and the next festival | `samsseasons.forecast`                               | everyone                |
| `/seasons date [world]`                            | Today's in-game date                              | `samsseasons.use`                                    | everyone                |
| `/seasons biome`                                   | The biome you stand in and how it looks right now | `samsseasons.biome`                                  | everyone                |
| `/seasons temperature`                             | How warm you are, and why                         | `samsseasons.temperature`                            | everyone                |
| `/seasons particles [on\|` /seasons actionbar \[on | off]\`                                            | Show or hide the temperature action bar for yourself | `samsseasons.actionbar` |
| off]\`                                             | Turn seasonal particles on or off for yourself    | `samsseasons.particles`                              | everyone                |

***

### Admin Commands

| Command                                                    | Description                                             | Permission                       |
| ---------------------------------------------------------- | ------------------------------------------------------- | -------------------------------- |
| `/seasons set <season> [phase] [world]`                    | Change the season (phase: `early`, `mid`, `late`)       | `samsseasons.admin.set`          |
| `/seasons next [world]`                                    | Skip to the next season                                 | `samsseasons.admin.next`         |
| `/seasons pause [world]`                                   | Freeze the seasonal clock                               | `samsseasons.admin.pause`        |
| `/seasons resume [world]`                                  | Let the seasons move on again                           | `samsseasons.admin.resume`       |
| `/seasons disable [world]`                                 | Switch the seasons off in a world (saved in config.yml) | `samsseasons.admin.disable`      |
| `/seasons enable [world]`                                  | Switch them back on; the world continues where it was   | `samsseasons.admin.disable`      |
| `/seasons setdate <day> <month> [year] [world]`            | Set the in-game date                                    | `samsseasons.admin.set`          |
| `/seasons festival list`                                   | List every festival and when it comes                   | `samsseasons.admin.festival`     |
| `/seasons festival start <festival> [world]`               | Start a festival now                                    | `samsseasons.admin.festival`     |
| `/seasons festival stop [festival] [world]`                | End the running festival                                | `samsseasons.admin.festival`     |
| `/seasons give <player> <season> <catch> [amount]`         | Give a seasonal fishing catch                           | `samsseasons.admin.give`         |
| `/seasons temperature <player>`                            | See another player's temperature                        | `samsseasons.temperature.others` |
| `/seasons temperature modify <player> <degrees> <seconds>` | Warm or cool a player for a while                       | `samsseasons.admin.temperature`  |
| `/seasons temperature clear <player>`                      | Remove those changes                                    | `samsseasons.admin.temperature`  |
| `/seasons editor`                                          | Open the in-game editor (needs the editor addon)        | `samsseasons.admin.editor`       |
| `/seasons reload`                                          | Reload configs, seasons, worlds and language            | `samsseasons.admin.reload`       |

{% hint style="info" %}
Worlds in `calendar` clock mode follow the real date, so `set`, `next`, `pause` and `resume` are locked there. The same goes for worlds that share another world's calendar: change the main world instead.
{% endhint %}

***

## Permission Nodes

| Permission                       | Description                       | Default |
| -------------------------------- | --------------------------------- | ------- |
| `samsseasons.admin`              | Everything below                  | op      |
| `samsseasons.use`                | Base access to `/seasons`         | true    |
| `samsseasons.menu`               | Season overview menu              | true    |
| `samsseasons.calendar`           | `/calendar`                       | true    |
| `samsseasons.info`               | `/seasons info`                   | true    |
| `samsseasons.forecast`           | `/seasons forecast`               | true    |
| `samsseasons.biome`              | `/seasons biome`                  | true    |
| `samsseasons.particles`          | Toggle own particles              | true    |
| `samsseasons.actionbar`          | Toggle own temperature action bar | true    |
| `samsseasons.temperature`        | See own temperature               | true    |
| `samsseasons.temperature.others` | See others' temperature           | op      |
| `samsseasons.admin.set`          | `set` and `setdate`               | op      |
| `samsseasons.admin.next`         | `next`                            | op      |
| `samsseasons.admin.pause`        | `pause`                           | op      |
| `samsseasons.admin.resume`       | `resume`                          | op      |
| `samsseasons.admin.disable`      | `disable` and `enable`            | op      |
| `samsseasons.admin.festival`     | `festival`                        | op      |
| `samsseasons.admin.give`         | `give`                            | op      |
| `samsseasons.admin.temperature`  | `temperature modify/clear`        | op      |
| `samsseasons.admin.editor`       | `editor`                          | op      |
| `samsseasons.admin.reload`       | `reload`                          | op      |
| `samsseasons.notify`             | Told about new versions on join   | op      |
| `samsseasons.bypass.temperature` | Never feel cold or heat           | false   |

{% hint style="warning" %}
`samsseasons.bypass.temperature` is **not** given to operators by default, so admins feel the weather like everyone else. Grant it on purpose (e.g. to staff in a build world).
{% endhint %}
