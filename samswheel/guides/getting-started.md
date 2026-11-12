---
description: Learn how to install and configure SamsWheel! :)
icon: rocket
---

# Getting Started

## Getting Started <a href="#getting-started" id="getting-started"></a>

Welcome to SamsWheel! This guide will walk you through the installation process and setting and spinning up your first wheel in-game!

{% hint style="info" %}
### **Requirements**

* **Java 21** or higher.
* **Paper 1.21.+** (or a fork like Purpur).
* A valid license key from our [Discord](https://discord.gg/KrvMkMDE2W).
{% endhint %}

***

## Installation

{% stepper %}
{% step %}
### Download and Install

Place the `SamsWheel.jar` file into your server's `plugins/` folder.
{% endstep %}

{% step %}
### Initial Startup

Start your server to generate the default configuration files. The plugin will initially disable itself until you provide a license key.
{% endstep %}

{% step %}
### Get a License

First, join our Discord server and create a ticket. After that, we will provide you with a license.
{% endstep %}

{% step %}
### Configure License

Open `plugins/SamsRank/config.yml` and enter your credentials:

```
license:
  license_key: "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx"
```
{% endstep %}

{% step %}
### Restart

Restart your server. Upon a successful license check, the plugin will detect your platform (ItemsAdder, Nexo, or Vanilla) and print a startup banner.
{% endstep %}
{% endstepper %}

***

## Resource Pack

SamsWheel installs its assets automatically:

* If **ItemsAdder** or **Nexo** is present, it merges into their pack.
* Otherwise, it can host its own pack over a built-in HTTP server see the Resource Pack Provider config section.

{% hint style="info" %}
After changing any wheel texture, custom design, or icon, regenerate/re-apply your resource pack so clients pick up the new assets.
{% endhint %}

***

## Your First Wheel

{% stepper %}
{% step %}
### Create it

```
/samswheel create example
```

This creates a wheel with the id `example`. Three example wheels (`daily`, `premium`, `vote`) also ship with the plugin.
{% endstep %}

{% step %}
### Place it

Stand where you want the wheel, look in the direction it should face, and run:

```
/samswheel move example
```

The wheel spawns a few blocks in front of you so it never sits inside the editor UI.
{% endstep %}

{% step %}
### Edit it

```
/samswheel editor
```

Opens the in-game editor. Pick your wheel and configure rewards, cost, animation, appearance and more.. see [Wheel Setup](wheel-setup.md).
{% endstep %}

{% step %}
### Spin it

Right-click the wheel in the world. If it costs a ticket or money, make sure you have it (or use `samswheel.bypass.cost`).
{% endstep %}
{% endstepper %}
