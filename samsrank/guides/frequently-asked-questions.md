---
description: Frequently asked questions about SamsRank
icon: circle-question
---

# Frequently Asked Questions

## Frequently Asked Questions

Answers to the most common questions.

***

## Licensing

<details>

<summary>How do I get a license key?</summary>

Register on [ranktags.samscreations.eu](https://ranktags.samscreations.eu), then join our [Discord](https://discord.gg/KrvMkMDE2W) and open a ticket.

</details>

<details>

<summary>What happens if the license server is down?</summary>

If the server is unreachable or rate-limited, SamsRank stays enabled and retries in the background before disabling itself, so tags don't break during short outages.

</details>

<details>

<summary>My license failed after moving servers.</summary>

Licenses are tied to a limited number of IPs. Open a ticket on [Discord](https://discord.gg/KrvMkMDE2W) for an IP reset. See License Troubleshooting.

</details>

***

## Tags & Effects

<details>

<summary>My tag shows as a box / [] / nothing.</summary>

The player doesn't have the current resource pack. Run `/samsrank reload` (on ItemsAdder, wait for `/iazip` to finish), then have the player rejoin. `/samsrank report` lists any rank that is missing its character (under **Missing glyphs**).

</details>

<details>

<summary>The effect doesn't animate.</summary>

* Check `effects.enabled` is `true`.
* Make sure the pack was regenerated after updating SamsRank and the player rejoined.
* On 26.3, your ItemsAdder / Nexo build must support 26.3 too.
* Using BetterHud? Keep `integrations.betterhud: true` - see BetterHud.

</details>

<details>

<summary>TAB / chat says "Legacy formatting codes have been detected".</summary>

Your plugin reads placeholders as MiniMessage. Set `placeholders.output-format: minimessage` - see Placeholders.

</details>

<details>

<summary>Can Bedrock players see the tags?</summary>

Yes - with Geyser, automatically. They see the static tag (effects are Java-only). See Bedrock (Geyser).

</details>

***

## In-Game Editor

<details>

<summary>The UI is too big or too small.</summary>

Tune `ui.rendering.hud-scale-divisor` in `config.yml`. A **smaller** number makes the UI **bigger**. The default suits around 80-90 FOV.

</details>

<details>

<summary>How do I close the UI?</summary>

Press **F** (swap hands). **Q** goes back a screen. Both can be rebound under `ui.keybinds`.

</details>

<details>

<summary>Can staff look at ranks without changing them?</summary>

Yes - give them `samsrank.edit.view` instead of `samsrank.edit`.

</details>

***

## Conversion & Platforms

<details>

<summary>ItemsAdder or Nexo - which should I use?</summary>

Both are fully supported. If you already use one for custom items, stick with it. With both installed, `platform.preferred` chooses which one handles the ranks.

</details>

<details>

<summary>Why are my PNGs deleted after conversion?</summary>

`auto_delete.enabled` is `true` by default so ranks aren't converted twice. Set it to `false` to keep the source images.

</details>
