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

## Folder Customization <a href="#configuration-guide" id="configuration-guide"></a>

* **`folders.ranks`**: The root folder for source PNG images (Default: `ranks`).

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
