---
description: Here you can learn how bedrock support works!
icon: block-brick
---

# Bedrock (Geyser)

## Bedrock Players (Geyser)

SamsWheel works for Bedrock players joining through [Geyser](https://geysermc.org). They see the wheel with its real texture, the reward items, the names and the pointer, watch it spin, and win exactly the same rewards as Java players.

***

## What you need

|                                         | Where to get it                                                                                            | Why                                                                                      |
| --------------------------------------- | ---------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------- |
| **Geyser** (+ Floodgate if you use it)  | [geysermc.org](https://geysermc.org/download)                                                              | Lets Bedrock players join your Java server.                                              |
| **GeyserDisplayEntity** extension       | [GitHub releases](https://github.com/GeyserExtensionists/GeyserDisplayEntity/releases)                     | Geyser on its own can't draw _item displays_ the entities the wheel is built from.       |
| **GeyserDisplayEntity's resource pack** | [`packs` folder on its GitHub](https://github.com/GeyserExtensionists/GeyserDisplayEntity/tree/main/packs) | The extension doesn't install this itself. Without it Bedrock shows **no** wheel at all. |

***

## Whole Setup

{% stepper %}
{% step %}
#### Install the GeyserDisplayEntity extension

Download the build that matches **your Geyser version** and put the `.jar` in:

```
plugins/Geyser-Spigot/extensions/
```
{% endstep %}

{% step %}
#### Install the extension's resource pack

Download `GeyserDisplayEntityPack.mcpack` from the [`packs` folder](https://github.com/GeyserExtensionists/GeyserDisplayEntity/tree/main/packs) and put it in:

```
plugins/Geyser-Spigot/packs/
```

{% hint style="warning" %}
This is the step most people miss. If only the floating text shows on Bedrock and no wheel, this pack is almost always why.
{% endhint %}
{% endstep %}

{% step %}
#### Enable custom content in Geyser

In `plugins/Geyser-Spigot/config.yml` set:

```yaml
enable-custom-content: true
```
{% endstep %}

{% step %}
#### Restart the server

Geyser loads resource packs and custom items **only at startup**, so do a full restart (not `/reload`).

On startup SamsWheel prints either **✔ Bedrock (Geyser) ready** or a list of what's still missing.
{% endstep %}

{% step %}
#### Check it

Run `/samswheel bedrock` in-game or in the console. Every item should be green ✔.
{% endstep %}
{% endstepper %}

***

## Checking your setup -> `/samswheel bedrock`

`/samswheel bedrock [player]` (permission `samswheel.reload`) checks every piece Bedrock players need and tells you exactly how to fix anything missing:

| Check                                            | What it means                                                                                                          |
| ------------------------------------------------ | ---------------------------------------------------------------------------------------------------------------------- |
| Geyser is installed                              | Geyser-Spigot is on the server.                                                                                        |
| GeyserDisplayEntity extension is installed       | Its jar is in `extensions/`.                                                                                           |
| GeyserDisplayEntity has started                  | The extension actually loaded (its config folder exists). If not, it's usually a build for a different Geyser version. |
| GeyserDisplayEntity's resource pack is installed | A pack in `packs/` defines the extension's display entity.                                                             |
| GeyserDisplayEntity's model is in charge         | No other pack replaces its model, or SamsWheel fixes the pack order for you. See Converted server packs.               |
| SamsWheel's Bedrock pack is generated            | `packs/sams_wheel.mcpack` exists.                                                                                      |
| SamsWheel's spin and item mappings are generated | The extension's mapping file from SamsWheel exists.                                                                    |
| Geyser custom content is enabled                 | `enable-custom-content: true` in Geyser's config.                                                                      |

{% hint style="info" %}
Still stuck? Join the [Discord](https://discord.gg/KrvMkMDE2W), open a ticket, and include the output of `/samswheel bedrock`.
{% endhint %}

***

## Tuning the Bedrock wheel

Depending on your wheel size and reward items, things can sit slightly too high or too low. You can fix that **live, in-game, without a restart**.

| Command                                           | What it does                                                                                                         |
| ------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------- |
| `/samswheel bedrock tune`                         | Shows the current values of all five settings.                                                                       |
| `/samswheel bedrock tune height-offset <value>`   | Moves **everything** (disc, items, names, holograms) up, or down with a negative number. Default `-0.5`. Start here. |
| `/samswheel bedrock tune icon-lift <value>`       | Moves the **reward items** up (higher number) or down (lower number). Default `0.65`.                                |
| `/samswheel bedrock tune block-icon-lift <value>` | The same, for **block** rewards only (diamond block, beacon, emerald block...). Default `0.2`.                       |
| `/samswheel bedrock tune disc-lift <value>`       | Moves the **wheel disc and pointer** up, or down with a negative number. Default `0.0`.                              |
| `/samswheel bedrock tune label-lift <value>`      | Moves the **reward names** up, or down with a negative number. Default `0.0`.                                        |
|                                                   |                                                                                                                      |

***

## Step by Step Tutorial

{% stepper %}
{% step %}
#### Stand in front of a wheel on Bedrock

Join with a Bedrock client and look at a wheel that has both flat items and block rewards.
{% endstep %}

{% step %}
#### Line up the whole wheel first

Right-click the wheel on Bedrock: the spot that reacts is where the wheel really is. Move everything (disc, items, names and holograms) so it sits there (blocks, negative = down):

```
/samswheel bedrock tune height-offset -0.75
```
{% endstep %}

{% step %}
#### Then the disc

Compare with Java: the floating title should sit just above the pointer. If only the disc is off, nudge it:

```
/samswheel bedrock tune disc-lift -0.2
```
{% endstep %}

{% step %}
#### Fix the reward items

Items sitting **below** their segment? Raise `icon-lift`. Sitting **above** it? Lower it. Small steps of `0.2` work best:

```
/samswheel bedrock tune icon-lift 0.8
```
{% endstep %}

{% step %}
#### Fix the block rewards

Blocks are held differently on Bedrock, so they have their own setting:

```
/samswheel bedrock tune block-icon-lift 0.4
```
{% endstep %}

{% step %}
#### Fix the names

Names too far from their item? Move them up (or down with a negative value):

```
/samswheel bedrock tune label-lift 0.2
```
{% endstep %}

{% step %}
#### Done

The values are already saved in `config.yml` (`bedrock.height-offset`, `bedrock.icon-lift`, `bedrock.block-icon-lift`, `bedrock.label-lift`, `bedrock.disc-lift`), so they stay after restarts.
{% endstep %}
{% endstepper %}

{% hint style="info" %}
Java players are never affected. Everything on this page only changes what **Bedrock** players see.
{% endhint %}
