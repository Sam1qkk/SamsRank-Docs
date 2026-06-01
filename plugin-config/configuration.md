---
description: Detailed explanation of every setting in config.yml
icon: seal
---

# Configuration

## Configuration Guide <a href="#configuration-guide" id="configuration-guide"></a>

This page covers every setting available in the `config.yml` file. SamsHead offers deep customization for caching, rendering, and resource pack delivery.

***

## General Settings <a href="#configuration-guide" id="configuration-guide"></a>

* `language`: The language file to use from the `lang/` folder (e.g., `en_US`, `cs_CZ`).
* `debug`: Enables detailed logging for skin fetching and database operations.

***

## Skin Cache <a href="#configuration-guide" id="configuration-guide"></a>

{% hint style="info" %}
#### Persistence

SamsHead uses a SQLite database (`skins.db`) to persist skins across restarts, significantly reducing API calls to Mojang.
{% endhint %}

|          Option          |              Description              |    Default    |
| :----------------------: | :-----------------------------------: | :-----------: |
|      cache.duration      |  Seconds before a skin is re-fetched. | `86400` (24h) |
|      cache.max-size      |       Max skins held in memory.       |      500      |
| cache.auto-cache-on-join | Pre-fetches skin when a player joins. |      true     |

***

## Rendering Options <a href="#configuration-guide" id="configuration-guide"></a>

#### `render.default-layer` <a href="#renderdefault-layer" id="renderdefault-layer"></a>

Determines the default look of avatars if not specified in the placeholder.

* `face`: Base skin layer only.
* `head`: Base skin + hat/overlay layer (Recommended).

#### `render.sizes` <a href="#rendersizes" id="rendersizes"></a>

Defines the pixel height of the rendered avatar for each preset. Values can range from 1 to 64.

```
sizes:
  small: 4
  medium: 8
  normal: 12
  large: 16
  giant: 32
```

***

## ResourcePack Provider <a href="#configuration-guide" id="configuration-guide"></a>

* Used when no external platform (ItemsAdder/Nexo) is detected.

{% hint style="warning" %}
#### Firewall

If using the internal server, ensure the port (default `8765`) is open in your server's firewall.
{% endhint %}

* `serve.enabled`: Whether to run the internal HTTP server.
* `serve.host`: Your public IP. Leave empty to auto-detect.
* `serve.url`: If you host the `pack.zip` elsewhere, enter the direct link here.
* `serve.required`: If true, players cannot play without accepting the pack.
