---
description: Learn how to install and configure SamsRank! :)
icon: rocket
---

# Getting Started

## Getting Started <a href="#getting-started" id="getting-started"></a>

Welcome to SamsRank! This guide will walk you through the installation process and initial configuration to get your custom rank tags working in-game.

{% hint style="info" %}
### **Requirements**

* **Java 21** or higher.
* **Paper 1.21+** (or Purpur/Folia).
* A valid license key from our [Discord](https://discord.gg/KrvMkMDE2W).
{% endhint %}

***

## Installation

{% stepper %}
{% step %}
### Download and Install

Place the `SamsRank.jar` file into your server's `plugins/` folder.
{% endstep %}

{% step %}
### Initial Startup

Start your server to generate the default configuration files. The plugin will initially disable itself until you provide a license key.
{% endstep %}

{% step %}
### Register

First, you need to register on the website [https://ranktags.samscreations.eu/](https://ranktags.samscreations.eu/). Then join our Discord server and create a ticket. After that, we will provide you with a license.
{% endstep %}

{% step %}
### Configure License

Open `plugins/SamsRank/config.yml` and enter your credentials:

```
license:
  discord_username: "your_username"
  license_key: "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx"
```
{% endstep %}

{% step %}
### Restart

Restart your server. Upon a successful license check, the plugin will detect your platform (ItemsAdder, Nexo, or Vanilla) and print a startup banner.
{% endstep %}
{% endstepper %}

***

Your First Rank


SamsRank ships with an `example` rank so you can test right away.

{% stepper %}
{% step %}
### Get a Tag

Design one on the [web generator](https://ranktags.samscreations.eu/dashboard), draw one in the [in-game editor](https://github.com/Sam1qkk/SamsRank/blob/main/docs/guides/in-game-editor.md) (`/samsrank`), or drop any `.png` into `plugins/SamsRank/ranks/`.&#x20;
{% endstep %}

{% step %}
### Convert It

SamsRank generates the font, configs, textures and shaders - see the [Conversion Tutorial](https://github.com/Sam1qkk/SamsRank/blob/main/docs/guides/conversion-tutorial.md).&#x20;
{% endstep %}

{% step %}
### Reload the Pack&#xD;

On ItemsAdder or Nexo, SamsRank asks the platform to rebuild its pack for you. Players rejoin (or re-accept the pack) to see the new tag.
{% endstep %}

{% step %}
### Use It!

Put the placeholder anywhere PlaceholderAPI works, a LuckPerms prefix, TAB, chat format or hologram:

```
%samsrank_example%
%samsrank_aurora_example%
```

The second one shows the tag with the animated **aurora** effect. See [Placeholders](https://github.com/Sam1qkk/SamsRank/blob/main/docs/guides/placeholders.md) and [Rank Effects](https://github.com/Sam1qkk/SamsRank/blob/main/docs/guides/rank-effects.md).
{% endstep %}
{% endstepper %}

***

## Folder Structure

```
plugins/SamsRank/
├── config.yml              Global settings
├── char_map.yml            Which character each rank uses (managed for you)
├── ranks/                  Drop your raw .png rank tags here
├── resourcepack/           Built-in pack (Vanilla mode)
├── bedrock/                Generated Bedrock pack (when Geyser/Floodgate is installed)
├── debug/                  Output of /samsrank report
└── lang/                   Language files (en_US, sk_SK, cs_CZ, pl_PL)
```
