---
description: Welcome to the SamsHead documentation!
icon: house-chimney-window
---

# Home

## SamsHead <a href="#samshead" id="samshead"></a>

SamsHead provides pixel-perfect player head rendering via text, components, and resource pack fonts. It allows you to display high-quality player avatars in chat, holograms, and menus without the performance overhead of traditional player heads or entities.

{% hint style="success" %}
#### Lightweight & Fast

SamsHead uses a custom TTF font to render 8×8 pixel grids using standard text characters, making it significantly faster than using player head items or entities. All skin fetching is handled asynchronously to ensure zero impact on server ticks.
{% endhint %}

***

## Compatibility

{% tabs %}
{% tab title="Software" %}
* **Java:** 21+
* **Server Version:** 1.21+
* **Supported Software:** Spigot, Paper, Purpur
{% endtab %}

{% tab title="Integrations" %}
* **Required:** [PlaceholderAPI](https://www.spigotmc.org/resources/placeholderapi.6245/)
* **Optional:** [ItemsAdder](https://itemsadder.devs.beer/) or [Nexo](https://nexoplugin.com/)
* **Optional:** [SkinsRestorer](https://skinsrestorer.net/) (For cracked/offline skins)
{% endtab %}
{% endtabs %}

***

## Key Features

{% columns %}
{% column %}
{% hint style="warning" icon="wand-magic-sparkles" %}
#### **Pixel-perfect avatars**

Face-only or full head (with the hat overlay), in five sizes from `small` to `giant`
{% endhint %}
{% endcolumn %}

{% column %}
{% hint style="danger" icon="puzzle-piece" %}
#### Smart skin caching

They are cached by UUID (so a name change never leave duplicate) and persisted between restarts.
{% endhint %}
{% endcolumn %}
{% endcolumns %}

{% columns %}
{% column %}
{% hint style="info" icon="percent" %}
#### Nested placeholders

Feed another placeholder's output (a leaderboard name, for example) straight into an avatar!
{% endhint %}
{% endcolumn %}

{% column %}
{% hint style="success" icon="gear" %}
#### Render types

Greyscale, sepia, invert, colour tint and an optional coloured border, on any avatar or bust!
{% endhint %}
{% endcolumn %}
{% endcolumns %}

***

## Navigation

{% content-ref url="https://app.gitbook.com/s/4wdDx1csYVpdxQMLVhk3/guides" %}
[GUIDES](https://app.gitbook.com/s/4wdDx1csYVpdxQMLVhk3/guides)
{% endcontent-ref %}

{% content-ref url="https://app.gitbook.com/s/4wdDx1csYVpdxQMLVhk3/plugin-config" %}
[PLUGIN CONFIG](https://app.gitbook.com/s/4wdDx1csYVpdxQMLVhk3/plugin-config)
{% endcontent-ref %}

{% content-ref url="https://app.gitbook.com/s/4wdDx1csYVpdxQMLVhk3/developers" %}
[DEVELOPERS](https://app.gitbook.com/s/4wdDx1csYVpdxQMLVhk3/developers)
{% endcontent-ref %}



***

{% hint style="success" %}
#### Support me!

If you enjoy using SamsHead, feel free to [Buy me a coffee](https://ko-fi.com/sam1qk)! Thank you! 🧡
{% endhint %}
