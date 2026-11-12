---
description: Frequently asked questions about SamsWheel!
icon: circle-question
---

# Frequently Asked Questions

## Frequently Asked Questions

Find answers to common questions..

<details>

<summary>The wheel face or editor icons don't show up.</summary>

The resource pack isn't applied. If you run ItemsAdder/Nexo, regenerate/re-apply their pack after any texture change. Otherwise enable the built-in [Resource Pack Provider](resource-pack-hosting.md). Turn on `debug.resourcepack` to see exactly what's installed.

</details>

<details>

<summary>Can I place the same wheel in several spots?</summary>

Yes. In the editor's **Location** section, add extra copies they all render from one definition and spin in sync.

</details>

<details>

<summary>How do the odds work?</summary>

`chance` is a **weight**. A reward's real percentage is its weight ÷ the total weight of all active rewards. Disabling a reward raises everyone else's chance. See [Rewards](rewards.md).

</details>

<details>

<summary>What happens if a player logs off mid-spin?</summary>

Nothing is lost. Undelivered rewards are stored and handed out the next time the player joins.

</details>

<details>

<summary>Can players add their own wheel designs?</summary>

Admins can drop a folder of PNGs into `plugins/SamsWheel/wheel-designs/`, `/samswheel reload`, and re-apply the pack. See [Appearance & Designs](appearance-and-designs.md).

</details>

<details>

<summary>Blocks look wrong / too 3D on the wheel.</summary>

Set **Block items** to _Flat (2D)_ in the **Reward Items** section (the default), or _3D block_ for the isometric look. Only block rewards are affected.

</details>
