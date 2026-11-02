---
description: Reference for all SamsRank commands!
icon: square-terminal
---

# Commands & Permissions

## Commands

The base command is `/samsrank`, with the alias `/sr`.

{% hint style="info" %}
### Skip the commands

Almost everything here can be done visually in the [In-Game Editor](/broken/pages/56d25f05e033c18134825f166f1ecb3756869b26). Just run `/samsrank`.
{% endhint %}

| Command                             | Description                                                                                                       | Permission                              |
| ----------------------------------- | ----------------------------------------------------------------------------------------------------------------- | --------------------------------------- |
| `/samsrank`                         | Open the in-game rank manager and pixel editor.                                                                   | `samsrank.edit` or `samsrank.edit.view` |
| `/samsrank edit <rank>`             | Open the editor directly on a rank.                                                                               | `samsrank.edit` or `samsrank.edit.view` |
| `/samsrank help`                    | Show the command list.                                                                                            | `samsrank.use`                          |
| `/samsrank generator`               | Get a clickable link to the web generator.                                                                        | `samsrank.generator`                    |
| `/samsrank convert`                 | Convert every PNG in `ranks/` into rank tags.                                                                     | `samsrank.convert`                      |
| `/samsrank list [page]`             | Browse all ranks with a live preview; click to copy the placeholder.                                              | `samsrank.list`                         |
| `/samsrank effects [page]`          | Preview every animated effect on the example rank.                                                                | `samsrank.effects`                      |
| `/samsrank preview <rank> [effect]` | Show a rank (optionally with an effect) in chat.                                                                  | `samsrank.preview`                      |
| `/samsrank rename <old> <new>`      | Rename a rank and all of its files.                                                                               | `samsrank.rename`                       |
| `/samsrank delete <rank> [--force]` | Permanently delete a rank and its assets (asks for `/samsrank confirm`).                                          | `samsrank.delete`                       |
| `/samsrank cleanup`                 | Remove orphaned textures, configs, cache and char map entries.                                                    | `samsrank.cleanup`                      |
| `/samsrank reload`                  | Reload config and language, rebuild the pack and ask ItemsAdder/Nexo to re-send it.                               | `samsrank.reload`                       |
| `/samsrank bedrock [player]`        | Check the Bedrock (Geyser) setup and show how to fix anything missing; optionally whether a player is on Bedrock. | `samsrank.bedrock`                      |
| `/samsrank bedrock rebuild`         | Rebuild the Bedrock pack now.                                                                                     | `samsrank.bedrock`                      |
| `/samsrank bedrock scale <value>`   | Change the size of rank tags on Bedrock (`0.25` - `4`).                                                           | `samsrank.bedrock`                      |
| `/samsrank bedrock offset <value>`  | Move rank tags up (positive) or down (negative) on Bedrock (`-32` - `32`).                                        | `samsrank.bedrock`                      |
| `/samsrank info`                    | Plugin status, platform and rank counts.                                                                          | `samsrank.info`                         |
| `/samsrank report`                  | Write `plugins/SamsRank/debug/debug-report.txt` for support.                                                      | `samsrank.report`                       |

***

## Permissions

| Node                 | Description                                                           | Default |
| -------------------- | --------------------------------------------------------------------- | ------- |
| `samsrank.use`       | Base access to `/samsrank`.                                           | op      |
| `samsrank.edit`      | Full access to the in-game editor (view **and** change).              | op      |
| `samsrank.edit.view` | Open the editor **view-only** - browse every rank but change nothing. | false   |
| `samsrank.generator` | Use `/samsrank generator`.                                            | op      |
| `samsrank.generate`  | Use `/samsrank generate` and create ranks in the editor.              | op      |
| `samsrank.convert`   | Use `/samsrank convert`.                                              | op      |
| `samsrank.list`      | Use `/samsrank list`.                                                 | op      |
| `samsrank.effects`   | Use `/samsrank effects`.                                              | op      |
| `samsrank.preview`   | Use `/samsrank preview`.                                              | op      |
| `samsrank.rename`    | Use `/samsrank rename`.                                               | op      |
| `samsrank.delete`    | Use `/samsrank delete` / `remove`.                                    | op      |
| `samsrank.cleanup`   | Use `/samsrank cleanup`.                                              | op      |
| `samsrank.reload`    | Use `/samsrank reload`.                                               | op      |
| `samsrank.bedrock`   | Use `/samsrank bedrock` (checks, rebuild, scale, offset).             | op      |
| `samsrank.info`      | Use `/samsrank info`.                                                 | op      |
| `samsrank.report`    | Use `/samsrank report`.                                               | op      |
| `samsrank.notify`    | Receive the join info panel and update notices.                       | op      |
