---
description: Common license errors and how to fix them
icon: shield-exclamation
---

# License Troubleshooting

## License Troubleshooting

SamsRank verifies your license on startup and **disables itself** if it's missing or invalid. The console prints a clear banner explaining why.

{% hint style="info" %}
SamsRank needs **both** your `discord_username` and your `license_key`, exactly as registered on [ranktags.samscreations.eu](https://ranktags.samscreations.eu). Get a key from our [Discord](https://discord.gg/KrvMkMDE2W).
{% endhint %}

### "License credentials are not configured"

The values are missing or still the placeholders. Open `plugins/SamsRank/config.yml`:

```yaml
license:
  discord_username: "your_discord_username"
  license_key: "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx"
```

***

### "License Validation Failed"

The license was rejected. The banner tells you why:

* **Not found / invalid** - check for typos, extra spaces or quotes, and that the username matches your Discord handle exactly.
* **Deactivated** - the license was turned off; open a ticket.
* **Wrong product** - the key was issued for a different plugin.
* **IP blocked / too many IPs** - see below.

***

### "License Rate Limited" / IP limit reached

A key may be used from a limited number of IPs. If you're rate-limited, the plugin **stays enabled** and retries 3 times, 45 seconds apart. If it still fails, open a ticket on [Discord](https://discord.gg/KrvMkMDE2W) to reset your IPs.

***

### "License Request Failed"

The server couldn't reach `ranktags.samscreations.eu`. Check that outgoing HTTPS (port 443) isn't blocked by a firewall - transient network issues resolve on the next start.

{% hint style="success" %}
Need a new key, a transfer, or an IP reset? Open a ticket on our [Discord](https://discord.gg/KrvMkMDE2W) and we'll sort it out. 🧡
{% endhint %}
