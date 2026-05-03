---
description: Common license errors and how to fix them
icon: shield-exclamation
---

# License Troubleshooting

## License Troubleshooting <a href="#license-troubleshooting" id="license-troubleshooting"></a>

If SamsRank cannot verify your license, it will display a specific error message in the console. Below are the most common errors and how to resolve them.

***

## Common Error Messages <a href="#license-troubleshooting" id="license-troubleshooting"></a>

<details open>

<summary>License credentials are not configured</summary>

**Cause:** You haven't changed the default values in the `config.yml`.

**Solution:** Open `plugins/SamsRank/config.yml` and replace `your_discord_username` and the placeholder key with your actual details from our Discord.

</details>

<details open>

<summary>License Validation Failed: Too many IPs hit the license server</summary>

**Cause:** Your license is being used on more IP addresses than allowed by your plan.

**Solution:** If you have moved your server or are using a dynamic IP, join our [Discord](https://discord.gg/KrvMkMDE2W) and open a ticket to have your IP limit reset.

</details>

<details open>

<summary>License Validation Failed: Invalid license key</summary>

**Cause:** The license key provided does not exist in our database or doesn't match the username.

**Solution:** Double-check for typos. Ensure there are no trailing spaces and that the username matches your Discord handle exactly (case-sensitive).

</details>

<details open>

<summary>License Request Failed: Could not connect to the license server</summary>

**Cause:** Your server cannot reach `ranktags.samscreations.eu`.

**Solution:** Ensure your server has an active internet connection and that your firewall is not blocking outgoing HTTPS requests (Port 443).

</details>

***

## Rate Limiting Logic <a href="#license-troubleshooting" id="license-troubleshooting"></a>

{% hint style="info" %}
### Background Retries

If you see a **License Rate Limited** warning, do not panic! The plugin will stay enabled and attempt to retry 3 times with a 45-second delay between each attempt. If it still fails after all retries, the plugin will disable itself to protect the license.
{% endhint %}

***

## Still having issues? <a href="#license-troubleshooting" id="license-troubleshooting"></a>

{% embed url="https://discord.gg/KrvMkMDE2W" %}
