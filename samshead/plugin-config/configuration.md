---
description: Detailed explanation of every setting in config.yml
icon: gear
---

# Configuration

### Configuration Guide <a href="#configuration-guide" id="configuration-guide"></a>

This page covers every setting available in the `config.yml` file. SamsHead offers deep customization for caching, rendering, and resource pack delivery.

***

### Update Checker <a href="#configuration-guide-1" id="configuration-guide-1"></a>

* `update-checker.enabled`: Checks for new versions on startup.
* `update-checker.notify-on-join`: Alerts admins in chat if an update is available.

***

### Skin Cache <a href="#configuration-guide-2" id="configuration-guide-2"></a>

SamsHead uses a high-performance LRU (Least Recently Used) memory cache backed by a persistent SQLite database.

| Option                   | Description                                             | Default       |
| ------------------------ | ------------------------------------------------------- | ------------- |
| cache.duration           | Seconds before a skin is re-fetched (86400 = 24h).      | `86400` (24h) |
| cache.max-size           | Max skins held in memory before the oldest are evicted. | 500           |
| cache.auto-cache-on-join | Fetches the skin immediately when a player joins.       | true          |

{% hint style="info" %}
#### Persistence

Skins are saved in `skins.db`. This means that even after a server restart, player heads will load instantly without hitting Mojang's API limits.
{% endhint %}

***

### Rendering Options <a href="#configuration-guide-3" id="configuration-guide-3"></a>

#### `render.default-layer` <a href="#renderdefault-layer" id="renderdefault-layer"></a>

Sets the default look if not specified in the placeholder.

* `face`: Base skin layer only.
* `head`: Base skin + hat/overlay layer (Recommended).

#### `render.sizes` <a href="#rendersizes" id="rendersizes"></a>

Defines the pixel height for avatar presets.

{% hint style="info" %}
#### Scaling

These values determine the size in the Minecraft font system. A size of 8 matches standard character height.
{% endhint %}

```
sizes:
  small: 4
  medium: 8
  normal: 12
  large: 16
  giant: 32
```

***

### ResourcePack Server <a href="#configuration-guide-4" id="configuration-guide-4"></a>

* Only active in **Vanilla Mode** (when ItemsAdder/Nexo are not detected).

{% hint style="warning" %}
#### **Firewall**

Ensure port `8765` (or your custom port) is open in your firewall for the internal HTTP server to function.
{% endhint %}

* `serve.port`: The port for the internal web server.
* `serve.url`: A direct link to your pack if hosted externally (e.g., Dropbox/GitHub).
* `serve.send-on-join`: Automatically prompts players to download the pack.
* `serve.required`: Forces players to accept the pack to play.

***

### Startup Preload <a href="#configuration-guide-4" id="configuration-guide-4"></a>

You can specify player names to be cached immediately on startup. This is perfect for NPC heads or staff members to avoid "Loading..." text when players first see them.

```
preload:
  players:
    - Notch
    - Sam1qk_
```
