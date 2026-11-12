---
description: >-
  The editor is a separate, optional jar, so servers that don't want it don't
  load it.
icon: align-right
---

# In-Game Editor

## Installing

{% stepper %}
{% step %}
#### Drop It In

Put `SamsSeasons-Editor-<version>.jar` into `plugins/SamsSeasons/addons/`.
{% endstep %}

{% step %}
#### Restart

The startup banner says **"✔ Editor addon ready"**. The editor adds its interface art to the SamsSeasons resource pack (or to your ItemsAdder/Nexo pack) by itself.
{% endstep %}

{% step %}
#### Open It

Run `/seasons editor` (permission `samsseasons.admin.editor`).
{% endstep %}
{% endstepper %}

{% hint style="info" %}
The editor draws its screens with the resource pack, so the pack must be enabled (`resource-pack.enabled: true`, the default).
{% endhint %}

***

## What You Can Edit

* **Seasons**: length, transition, colour, and every per-season value in one place, split into tabs (World, Nature, Gameplay...) and sub-categories. Phase columns (early/mid/late) only show where a setting can differ per phase.
* **Items**: every seasonal fishing catch as the real item players get. Click one to edit it.
* **Mobs**: seasonal spawn rates and variants, shown as spawn eggs.
* **Modules**: switch whole features on or off: weather, festivals, wildlife, blooms, sky, snow, particles, temperature, the **calendar dates** and more.

Changes are written to the normal config files and applied at once.

***

## Addon Settings

The editor's own settings (look and controls only) are in `plugins/SamsSeasons/addons/SamsSeasons-Editor/config.yml`.
