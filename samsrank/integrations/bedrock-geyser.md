---
description: Here you can learn how bedrock support works!
icon: block-brick
---

# Bedrock (Geyser)

## How It Works

Bedrock can't read Java resource packs, so on its own a Bedrock player would see nothing where the tag should be. SamsRank solves this by building a small **Bedrock resource pack** with all your rank tags and handing it to Geyser, which sends it to every Bedrock player.

* **Same placeholders** -> nothing to change in TAB, chat or LuckPerms. The same text shows the tag on both editions.
* **Wide tags render whole** -> not squeezed into a square like most Bedrock emoji packs.
* **Static on Bedrock** -> animated effects are a Java shader feature. Effect placeholders simply show the plain tag to Bedrock players.
* Works with **ItemsAdder**, **Nexo** and **Vanilla** mode.

{% hint style="success" %}
With **Geyser 2.6.2+** on the same server, there's nothing to set up: the pack is sent on join, and new or changed ranks appear the next time a Bedrock player joins, no Geyser restart.
{% endhint %}

***

## Setup

{% tabs %}
{% tab title="Geyser on this server" %}
1. Install **Geyser-Spigot** (and **Floodgate**, if you use it).
2. Restart. SamsRank builds the pack and sends it to Bedrock players automatically.
3. Run `/samsrank bedrock` to check everything.

On Geyser older than 2.6.2, SamsRank copies the pack into Geyser's `packs/` folder instead - restart the server after adding or changing ranks (or update Geyser).
{% endtab %}

{% tab title="Geyser on a proxy" %}
SamsRank can't reach a Geyser that runs on Velocity/BungeeCord. Install **Floodgate** on the backend so SamsRank builds the pack, then:

1. Copy `plugins/SamsRank/bedrock/samsrank_bedrock.mcpack` into the **proxy's** `plugins/Geyser-*/packs/` folder.
2. Restart Geyser.
3. Repeat after adding or changing ranks.
{% endtab %}
{% endtabs %}

***

## Checking the Setup

```
/samsrank bedrock [player]
```

Shows a ✔ / ✘ checklist with a fix for anything missing:

* Geyser is installed (or runs on your proxy).
* The Bedrock pack is generated, and how many tags it holds.
* The pack is sent automatically (Geyser 2.6.2+).
* Every rank has a Bedrock tag (lists any that are missing).
* No other Bedrock pack replaces the same glyph pages.

Add a player name to see whether they're detected as Bedrock or Java.

***

## Size and Position

If tags look too big, too small, or sit a little too high or low next to the text, tune them live:

```
/samsrank bedrock scale <0.25-4>     # 1 = default size, lower = smaller
/samsrank bedrock offset <-32..32>   # positive = up, negative = down
```

Both save to `config.yml` and rebuild the pack instantly, **rejoin on Bedrock** to see the change. Tags scale in whole pixel steps to stay crisp, so small scale changes may look the same.

`/samsrank bedrock rebuild` rebuilds the pack by hand.
