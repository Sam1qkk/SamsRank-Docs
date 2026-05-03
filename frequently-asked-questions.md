---
description: Frequently asked questions about SamsRank
icon: circle-question
---

# Frequently Asked Questions

## Frequently Asked Questions <a href="#frequently-asked-questions" id="frequently-asked-questions"></a>

Find answers to common questions about licensing, configuration, and troubleshooting.

***

## Frequently Asked Questions <a href="#frequently-asked-questions" id="frequently-asked-questions"></a>

<details open>

<summary>How do I get a license key?</summary>

You can obtain a license key by joining our [Discord Server](https://discord.gg/KrvMkMDE2W) and opening a support ticket. Our team will assist you with the registration process.

</details>

<details open>

<summary>What happens if the license server is down?</summary>

SamsRank includes a built-in retry mechanism. If the server is unreachable or rate-limited, the plugin will remain active and attempt to verify in the background for several minutes before disabling itself. This ensures your server's visual elements don't break during brief outages.

</details>

<details open>

<summary>Why did my license fail after a server move?</summary>

Licenses are locked to specific IP addresses. If your server IP changes, the license system may flag it as "Too many IPs". You will need to request an IP reset in our Discord.

</details>

{% hint style="info" %}
### Detailed Troubleshooting

For a full list of error codes and explanations, check the [License Troubleshooting](https://kdr-202604-e3dnxpe8.kodari.wiki/guides/license-troubleshooting) page.
{% endhint %}

***

## Conversion & Platforms

<details open>

<summary>Which platform should I choose: ItemsAdder or Nexo?</summary>

SamsRank supports both! If you already use one of these for your custom items, stick with it. If you have both installed, you can use the `platform.preferred` setting in `config.yml` to choose which one handles the conversion and placeholders.

</details>

<details open>

<summary>Why are my PNGs deleted after conversion?</summary>

By default, the `auto_delete.enabled` setting is set to `true`. This keeps your `templates` folder clean by removing source images once they are safely packed into an export ZIP. You can disable this in the config if you prefer to keep them.

</details>
