---
description: Reference for all SamsHead commands!
icon: square-terminal
---

# Commands & Permissions

## Commands

All commands can be used with the `/samshead` or `/sh` prefix.

|     Command    | Description                                         |      Permission     |
| :------------: | --------------------------------------------------- | :-----------------: |
|   /sh reload   | Reloads config, language, and regenerates the pack. |   samshead.reload   |
| /sh clearcache | Wipes the memory cache and SQLite database.         | samshead.clearcache |
|   /sh genpack  | Manually forces a resource pack file generation.    |   samshead.genpack  |

***

## Permissions

* `samshead.use`: Access to the base command and help menu.
* `samshead.admin`: Includes all administrative permissions and update notifications on join.

{% hint style="info" %}
Tab completion is available for all subcommands and will dynamically show if `genpack` is needed based on your integration mode.
{% endhint %}
