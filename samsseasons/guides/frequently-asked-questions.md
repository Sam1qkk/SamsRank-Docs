---
description: Frequently asked questions about SamsSeasons!
icon: circle-question
---

# Frequently Asked Questions

## Frequently Asked Questions

<details>

<summary>The grass and leaves don't change colour.</summary>

Install PacketEvents; the colours are shown through it. The startup log tells you if it's missing. Also check that `atmosphere/biomes.yml` has `enabled: true`, and restart the server after changing it.

</details>

<details>

<summary>Only one of my worlds has seasons.</summary>

Set `worlds.enabled` to `- all` in `config.yml`. Older configs may still list `- world`. With `all`, worlds loaded by Multiverse get seasons too.

</details>

<details>

<summary>I changed a list in a config, but nothing happened after updating the plugin.</summary>

SamsSeasons adds _new_ settings to your files on update, but never overwrites lists or sections you already have, so your edits are safe. To get new defaults for one of them, delete that file (or the section) and run `/seasons reload`.

</details>

<details>

<summary>Players don't get the resource pack.</summary>

With `provider: auto` and no ItemsAdder/Nexo, SamsSeasons hosts the pack on `self-host.port`. That port must be open to the internet, and `hostname` must be your public IP or domain if auto-detection picks the wrong one. Behind a proxy or panel, use `url-override` or switch to ItemsAdder/Nexo.

</details>

<details>

<summary>Does it break my builds? What about the snow?</summary>

No. Snow, ice, flowers and mushrooms that SamsSeasons places are remembered per chunk, and only those are removed later, and only if they're still there. Leaf swaps (cherry blossom, birch) are purely visual.

</details>

<details>

<summary>Is it heavy on performance?</summary>

Particles and sky effects are per player and capped. Snow, blooms and wildlife only work near players. A TPS guard (`performance` in `config.yml`) scales effects down when the server struggles.

</details>

<details>

<summary>Can I make the whole server follow the real calendar?</summary>

Yes: `clock-mode: calendar` under `worlds.default`. Use `hemisphere: south` for southern seasons.

</details>

<details>

<summary>Does it support Folia or Bedrock?</summary>

Folia is not supported. Bedrock (Geyser) is not officially supported yet: the seasons run for everyone, but how much of the visuals a Bedrock player sees depends on Geyser.

</details>
