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

```
resource-pack:
  enabled: true
  port: 8765
  hostname: "your.server.ip" # Leave empty to auto-detect
  required: true             # Force players to accept the pack
  kick-message: "&cYou must accept the resource pack to play!"
```

***

## Automatic Updates <a href="#conversion-tutorial" id="conversion-tutorial"></a>

Whenever you run `/samsrank convert`, the plugin performs the following actions:

1. Rebuilds the `pack.zip` in the `resourcepack/` folder.
2. Notifies all online players to download the updated version.

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
