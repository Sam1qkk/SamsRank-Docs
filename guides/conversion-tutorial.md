---
description: Step-by-step guide to converting PNG rank tags
icon: gear
---

# Conversion Tutorial

## Conversion

SamsRank automates everything a custom rank tag needs: the font provider, ItemsAdder/Nexo configs, textures and the effect shaders.

{% stepper %}
{% step %}
#### Prepare images

Place your rank tag images (must be `.png`) into `plugins/SamsRank/ranks/`. The file name becomes the rank name, so `Owner.png` becomes the rank `owner`.
{% endstep %}

{% step %}
#### Run conversion

```
/samsrank convert
```

SamsRank will:

* Clean up the file names into valid rank names.
* Copy the textures into the right pack (ItemsAdder, Nexo or its own).
* Generate the ItemsAdder / Nexo configs (if detected).
* Give each rank its own character and write the font provider.
* Install the shaders for the animated Rank Effects.
{% endstep %}

{% step %}
#### Reload

```
/samsrank reload
```

On **ItemsAdder** and **Nexo**, SamsRank asks the platform to rebuild and re-send its pack for you (`iareload` + `iazip` / `nexo reload`). Players need to rejoin or re-accept the pack.
{% endstep %}

{% step %}
#### Verify

Use `/samsrank list` to see your ranks. Click any rank in chat to copy its placeholder to your clipboard.
{% endstep %}
{% endstepper %}

{% hint style="info" %}
#### **Auto-Delete**

By default, the source images in `ranks/` are deleted after a successful conversion so they aren't converted twice. Set `auto_delete.enabled: false` in the config to keep them.
{% endhint %}

***

## Tag Size

All tags share one size, set in `config.yml`:

```yaml
samsrank-resourcepack:
  height: 9   # how tall the tag is drawn (in font pixels)
  ascent: 8   # how far it sits above the text baseline (must be <= height)
```

After changing these, run `/samsrank convert` and regenerate your pack.

***

## Other Ways to Create Ranks

* **Web Generator** - design a tag online or generate one with `/samsrank generate`.
* **In-Game Editor** - create and draw ranks pixel by pixel with `/samsrank`.

Both save the PNG and convert it for you.

{% hint style="success" %}
Bedrock players get the same tags automatically, see Bedrock (Geyser).
{% endhint %}
