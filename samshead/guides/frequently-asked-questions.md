---
description: Frequently asked questions about SamsHead
icon: circle-question
---

# Frequently Asked Questions

## Frequently Asked Questions <a href="#frequently-asked-questions" id="frequently-asked-questions"></a>

Find answers to common questions..

***

<details>

<summary>Does this work with cracked/offline servers?</summary>

Yes! If you have **SkinsRestorer** installed, SamsHead will automatically detect it. It supports both premium and cracked skins, ensuring everyone has an avatar.

</details>

<details>

<summary>Why do I see weird squares or characters?</summary>

This means the resource pack isn't loaded. Players must accept the server resource pack. If you use ItemsAdder or Nexo, ensure you have reloaded their respective packs after installing SamsHead.

</details>

<details>

<summary>How do I force a skin refresh?</summary>

You can use `/sh clearcache` to wipe the database and memory, or simply wait for the `cache.duration` to expire. If using SkinsRestorer, the plugin refreshes automatically when a skin is changed.

</details>

<details>

<summary>Can I use this in my own plugin?</summary>

Absolutely. Check the [Developer API](https://kdr-202605-obdbla19.kodari.wiki/api-reference) section for instructions on hooking into our rendering engine.

</details>

<details>

<summary>What happens if Mojang's API is down?</summary>

SamsHead will use the persistent SQLite cache for any player who has joined before. For new players, it will fall back to a procedurally generated Steve or Alex face based on their name.

</details>

<details>

<summary>The bust placeholders are cutting off?</summary>

Minecraft has length limits for certain text fields (like scoreboards). Player busts are extremely long strings of colored characters. Only use busts in Chat, Holograms, or GUI Lore where long strings are supported.

</details>

<details>

<summary>The avatar is stuck on "Loading avatar"..</summary>

The skin hasn't been fetched yet, or the lookup is failing. The first request shows the loading text briefly, then the avatar appears once the async fetch finishes. If it never resolves, enable `debug.skins` and check the console, or run `/samshead debug`.

</details>

<details>

<summary>The heads sit slightly too high or too low..</summary>

Set **`render.y-position`** in config.yml. Positive moves every avatar/bust **down**, negative **up**, in whole pixels. Run `/samshead reload` (or `/samshead genpack` in vanilla mode) afterwards so the font regenerates.

</details>
