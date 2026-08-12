---
description: Detailed explanation of every setting in config.yml
icon: seal
---

# Configuration

## Configuration Guide <a href="#configuration-guide" id="configuration-guide"></a>

This page covers every setting available in the `config.yml` file. SamsRank uses an auto-patching system that injects new settings into your existing file without overwriting your changes.

***

## License Settings <a href="#configuration-guide" id="configuration-guide"></a>

{% hint style="warning" %}
### Required

You must configure these values for the plugin to function. Join our [Discord](https://discord.gg/KrvMkMDE2W) to get a key.
{% endhint %}

* **`license.discord_username`**: The Discord handle associated with your purchase.
* **`license.license_key`**: Your unique UUID license key.

***

## Platform Settings <a href="#configuration-guide" id="configuration-guide"></a>

* **`platform.preferred`**:
  * `itemsadder`: Forces ItemsAdder mode.
  * `nexo`: Forces Nexo mode.
  * `both`: Enables both (default).

***

## Auto Delete <a href="#configuration-guide" id="configuration-guide"></a>

* **`auto_delete.enabled`**: If `true`, source PNGs are removed after successful conversion to keep the workspace clean.

***

## ResourcePack Provider <a href="#configuration-guide" id="configuration-guide"></a>

Used when no external platform (ItemsAdder/Nexo) is detected.

* **`resource-pack.enabled`**: Enables the built-in HTTP server.
* **`resource-pack.port`**: The port for the web server (Default: `8765`).
* **`resource-pack.hostname`**: Public IP/Domain for the download link.
* **`resource-pack.required`**: If `true`, players are kicked if they decline the pack.

***

## ResourcePack Settings <a href="#configuration-guide" id="configuration-guide"></a>

* **`samsrank-resourcepack.height`**: Rendered glyph height (Default: `9`).
* **`samsrank-resourcepack.ascent`**: Vertical position offset (Default: `8`).

***

## UI Rendering Settings

These settings control how the In-Game Interface is positioned and scaled in your view.

* **`ui.cursor.sensitivity`**: How fast the cursor moves. Higher = faster (Default: `4.0`).
* **`ui.rendering.hud-scale-divisor`**: The master size knob. A **smaller** number makes the UI **bigger** (Default: `762.5`).
* **`ui.rendering.anchor-forward-offset`**: Distance (in blocks) the UI sits in front of you. 0.8 is close enough to avoid most wall clipping. (Default: `0.8`).
* **`ui.rendering.canvas-offset-y`**: Vertical nudge to center the UI on your screen. (Default: `470.0`).
