---
description: Reference for all SamsWheel commands!
icon: square-terminal
---

# Commands & Permissions

## Commands

All commands can be used with the `/samswheel`, with the aliases `/sw` and `/wheel`.

{% hint style="info" %}
#### Skip the Commands

You can perform all these steps visually using the In-Game Editor. Simply run `/samswheel editor` to manage your wheels without typing long commands.
{% endhint %}

| Command                                                    | Description                                                                                                                | Permission                                       |
| ---------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------ |
| `/samswheel help`                                          | Show the command list.                                                                                                     | `samswheel.use`                                  |
| `/samswheel list`                                          | List every configured wheel.                                                                                               | `samswheel.use`                                  |
| `/samswheel spin [wheel]`                                  | Spin the wheel you're standing at (or a named one) without clicking it handy for Bedrock players.                          | `samswheel.use`                                  |
| `/samswheel editor`                                        | Open the in-game editor.                                                                                                   | `samswheel.editor`                               |
| `/samswheel create <id>`                                   | Create a new wheel.                                                                                                        | `samswheel.create`                               |
| `/samswheel remove <id>`                                   | Delete a wheel.                                                                                                            | `samswheel.remove`                               |
| `/samswheel move <id>`                                     | Move the wheel to your location.                                                                                           | `samswheel.move`                                 |
| `/samswheel setdirection <id>`                             | Turn the wheel to face you.                                                                                                | `samswheel.move`                                 |
| `/samswheel reload`                                        | Reload config, language and wheels.                                                                                        | `samswheel.reload`                               |
| `/samswheel bedrock [player]`                              | Check the Bedrock (Geyser) setup and show how to fix anything missing; optionally whether a player is detected as Bedrock. | `samswheel.reload`                               |
| `/samswheel give <player> <wheel> <amount>`                | Give free spins.                                                                                                           | `samswheel.give`                                 |
| `/samswheel take <player> <wheel> <amount>`                | Take free spins.                                                                                                           | `samswheel.take`                                 |
| `/samswheel ticket <give\|take> <player> <wheel> <amount>` | Give or take the wheel's ticket item.                                                                                      | `samswheel.give` / `samswheel.take`              |
| `/samswheel stats [player]`                                | Show spin statistics.                                                                                                      | `samswheel.stats`                                |
| `/samswheel resetcooldown <player> <wheel>`                | Reset a player's cooldown.                                                                                                 | `samswheel.admin` or `samswheel.bypass.cooldown` |
