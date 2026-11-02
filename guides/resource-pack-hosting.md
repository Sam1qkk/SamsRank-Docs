---
description: How to use the built-in HTTP server to host your pack
icon: server
---

# Resource Pack Hosting

## ResourcePack Hosting <a href="#conversion-tutorial" id="conversion-tutorial"></a>

SamsRank includes a built-in HTTP server. This allows the plugin to host the generated `pack.zip` directly from your server, eliminating the need for external hosting services like Dropbox or MCPacks.

{% hint style="warning" %}
### **Network Requirement**

The port you choose (default `8765`) must be open in your firewall (TCP) and correctly port-forwarded if you are not on a dedicated host.
{% endhint %}

***

## Configuration <a href="#conversion-tutorial" id="conversion-tutorial"></a>

If you are not using ItemsAdder or Nexo (which handle their own hosting), you can enable the internal server in `config.yml`:

```yaml
resource-pack:
  enabled: true
  port: 8765
  hostname: ""          # public IP or domain, leave empty to auto-detect
  url-override: ""      # use your own URL instead (e.g. behind a CDN)
  required: false       # kick players who decline or fail to download
  max-retries: 3        # re-send the pack this many times if a download fails
  kick-message: "&cYou must accept the resource pack to play on this server."
```

***

## Automatic Updates <a href="#conversion-tutorial" id="conversion-tutorial"></a>

Whenever ranks change (`/samsrank convert`, the editor, `/samsrank reload`), SamsRank:

1. Rebuilds `pack.zip` from the `resourcepack/` folder.
2. Sends the updated pack to online players.

***

## Troubleshooting <a href="#conversion-tutorial" id="conversion-tutorial"></a>

<details open>

<summary><strong>Port is already in use</strong></summary>

If you see a warning that port `8765` is in use, check if another plugin (like SimpleVoiceChat or another web server) is using it. Change the `port` in `config.yml` to another 4 or 5-digit number.

</details>

<details open>

<summary><strong>Players see 'Download Failed'</strong></summary>

Ensure your `hostname` is correct. If you are using a proxy (like Cloudflare), you must use your actual public IP or a direct subdomain that isn't proxied, as Minecraft clients need a direct connection to download the zip.

</details>

<details>

<summary><strong>The pack doesn't start downloading for some players</strong></summary>

Turn on `debug.resourcepack` in `config.yml`. It logs every send, retry, each player's download status and every HTTP request. `max-retries` re-sends the pack automatically when a download is dropped.

</details>
