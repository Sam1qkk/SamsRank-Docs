---
description: Learn how to install and configure SamsHead! :)
icon: rocket
---

# Getting Started

## Getting Started <a href="#getting-started" id="getting-started"></a>

Welcome to SamsHead! This guide will walk you through the installation process and initial configuration to get pixel-perfect player avatars working in-game.

{% hint style="info" %}
### **Requirements**

* **Java 21** or higher.
* **Paper 1.21+** (or derivatives like Purpur).
* **PlaceholderAPI** (Highly recommended).
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

Start your server to generate the default configuration files.
{% endstep %}

{% step %}
### ResourcePack Integration

SamsHead automatically detects your environment:

* **ItemsAdder/Nexo**: Files are written directly to their respective content folders.
* **Vanilla**: A built-in HTTP server starts on port `8765` to serve the pack.
{% endstep %}

{% step %}
### Reload and Verify

Reload your resource pack. Use `/sh reload` to ensure everything is synced. You should see a success message in the console showing the number of cached skins.
{% endstep %}
{% endstepper %}
