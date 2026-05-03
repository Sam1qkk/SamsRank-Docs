---
description: Step-by-step guide to converting PNG rank tags
icon: gear
---

# Conversion Tutorial

## Conversion Tutorial <a href="#conversion-tutorial" id="conversion-tutorial"></a>

SamsRank automates the process of generating configurations, font providers, and shaders for your rank tags.

***

## Conversion

{% stepper %}
{% step %}
### Prepare images

Place your rank tag images (must be `.png`) into the `plugins/SamsRank/ranks/` folder.
{% endstep %}

{% step %}
### Run conversion

Run the command `/samsrank convert`.

SamsRank will:

* Optimize the filenames.
* Copy textures to the resource pack.
* Generate ItemsAdder/Nexo configs (if detected).
* Update the `default.json` font provider.
* Inject custom shaders for **Rank Effects**.
{% endstep %}

{% step %}
### Reload

Reload the plugin using `/samsrank reload`. If you are using ItemsAdder, run `/iareload` and then `/iazip`. If you are using Nexo, run `/nexo reload`.
{% endstep %}

{% step %}
### Verify

Use `/samsrank list` to see your ranks. You can click on any rank in the chat to copy its PlaceholderAPI format directly to your clipboard.
{% endstep %}
{% endstepper %}

***

## Rank Effects (Shaders) <a href="#conversion-tutorial" id="conversion-tutorial"></a>

One of the most powerful features of the conversion is the automatic injection of shaders. This allows you to apply animations to your ranks using placeholders.

**Example Placeholder:** `%samsrank_starlight_admin%`

This would display the `admin` rank with a diagonal shimmering effect. You can see all available effects using `/samsrank effects`.



{% hint style="info" %}
### **Auto-Delete:**

By default, the plugin deletes the source images from `ranks/` after a successful conversion to prevent duplicates. You can disable this by setting `auto_delete.enabled: false` in the config.
{% endhint %}
