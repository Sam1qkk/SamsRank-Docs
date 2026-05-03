---
description: Learn how to install and configure SamsRank! :)
icon: rocket
---

# Getting Started

## Getting Started <a href="#getting-started" id="getting-started"></a>

Welcome to SamsRank! This guide will walk you through the installation process and initial configuration to get your custom rank tags working in-game.

{% hint style="info" %}
### **Requirements:**

* **Java 21** or higher.
* **Paper 1.21+** (or derivatives like Purpur/Folia).
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

## Folder Structure

SamsRank uses a simplified single-folder system for all platforms:

* `plugins/SamsRank/ranks/`: Drop all your raw `.png` rank templates here.
* `plugins/SamsRank/resourcepack/`: The built-in resource pack is generated here.
* `plugins/SamsRank/lang/`: Language files for plugin messages.

***

## Basic Commands

| Command             | Description                            | Permission         |
| ------------------- | -------------------------------------- | ------------------ |
| `/samsrank convert` | Converts PNGs in the ranks folder      | `samsrank.convert` |
| `/samsrank list`    | Interactive preview of converted ranks | `samsrank.list`    |
| `/samsrank effects` | Browse shader-based rank effects       | `samsrank.effects` |
| `/samsrank reload`  | Reload config and update resource pack | `samsrank.reload`  |
