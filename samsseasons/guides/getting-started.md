---
description: Learn how to install SamsSeasons and see your first season change! :)
icon: rocket
---

# Getting Started

## Getting Started

This guide walks you through installation, the license step, and the first things worth trying in-game.

{% hint style="info" %}
#### **Requirements**

* **Java 21** or higher (Java 25+ on Paper 26.x).
* **Paper 1.21.8** or newer (or a fork like Purpur).
* **PacketEvents** (recommended) for the seasonal grass, leaf and water colours.
* A valid license key from our [Discord](https://discord.gg/KrvMkMDE2W).
{% endhint %}

***

## Installation

{% stepper %}
{% step %}
#### Download and Install

Put `SamsSeasons-<version>.jar` into your server's `plugins/` folder. For the seasonal colours, also install [PacketEvents](https://modrinth.com/plugin/packetevents).
{% endstep %}

{% step %}
#### Initial Startup

Start your server. SamsSeasons creates its files in `plugins/SamsSeasons/` and registers its seasonal biome datapack by itself. There's nothing to install by hand.
{% endstep %}

{% step %}
#### Configure License

Open `plugins/SamsSeasons/config.yml` and enter your key:

```yaml
license:
  license_key: "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx"
```
{% endstep %}

{% step %}
#### Restart

Restart the server. The startup banner shows the version, your server software and how many worlds have seasons.
{% endstep %}
{% endstepper %}

***

## First Steps In-Game

* `/seasons` opens the **season overview**: the current season, temperature, forecast, the next festival and the calendar.
* `/seasons set winter` jumps straight to winter. Watch the leaves turn white and snow start to settle.
* `/seasons next` skips ahead to the next season.
* `/seasons forecast` shows the weather for the coming days.
* `/seasons temperature` shows how warm you are, and why.

{% hint style="success" %}
#### **Where are my seasons?**

By default every overworld-type world has seasons (`worlds.enabled: [all]`), including worlds loaded later by Multiverse. The Nether and the End stay vanilla. See Seasons, Calendar & Worlds.
{% endhint %}

***

### The Plugin Folder

```
plugins/SamsSeasons/
├── config.yml          language, worlds, announcements, resource pack
├── seasons.yml         the four seasons + calendar
├── atmosphere/         biomes, particles, snow, weather, sky, blooms, daylight, ambience
├── gameplay/           temperature, crops, animals, mobs, fishing, wildlife, festivals
├── gui/                season-menu.yml, calendar.yml
├── worlds/             optional per-world overrides
├── lang/               all messages, in 6 languages
├── addons/             addon jars (the editor)
└── internal/           data and the generated resource pack (don't edit)
```

Changed something? Run `/seasons reload`. Biome colours in `atmosphere/biomes.yml` are the one exception: they need a restart.
