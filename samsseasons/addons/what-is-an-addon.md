---
description: Here you will learn what addon is!
icon: cowbell-circle-plus
---

# What Is an Addon?

## What Is an Addon?

An addon is a small extra jar that adds a feature to SamsSeasons. It isn't a plugin of its own: it doesn't go into `plugins/`, and it only runs together with SamsSeasons.

***

### Why Addons?

Some features only matter to some servers. The in-game editor, for example, is only used by admins while setting up. Shipping it as an addon keeps SamsSeasons lean:

* **You choose what runs.** No editor jar, no editor code loaded, no editor art in the resource pack.
* **Updates stay separate.** An addon can be updated without touching your SamsSeasons configs.
* **Nothing to set up.** Drop the jar in, restart, done.

{% hint style="info" %}
The **SamsSeasons-Editor** addon comes with your purchase. See In-Game Editor.
{% endhint %}

***

## Installing an Addon

{% stepper %}
{% step %}
#### Start SamsSeasons Once

The `plugins/SamsSeasons/addons/` folder is created on the first start.
{% endstep %}

{% step %}
#### Drop the Jar In

Put the addon jar into `plugins/SamsSeasons/addons/`, **not** into `plugins/`.

```
plugins/
├── SamsSeasons-1.0.0.jar
└── SamsSeasons/
    └── addons/
        ├── SamsSeasons-Editor-1.0.0.jar      <- the addon
        └── SamsSeasons-Editor/
            └── config.yml                    <- its settings (created by the addon)
```
{% endstep %}

{% step %}
#### Restart the Server

Addons load when SamsSeasons starts, before the resource pack is built, so their art is included straight away. The startup banner confirms a loaded addon (e.g. **"✔ Editor addon ready"**).
{% endstep %}
{% endstepper %}

***

## Updating or Removing

* **Update:** stop the server, replace the jar, start again. Its settings in `addons/<Addon>/` stay.
* **Remove:** stop the server and delete the jar. SamsSeasons runs exactly as before, and the addon's art leaves the resource pack on the next start.
* `/seasons reload` also reloads every addon's settings.

{% hint style="warning" %}
Addons are loaded on startup only. Adding or removing a jar needs a **restart**, not `/seasons reload`, and never a plugin manager like PlugMan.
{% endhint %}

### Troubleshooting

| Console message                              | Meaning                                                                                |
| -------------------------------------------- | -------------------------------------------------------------------------------------- |
| `Addon <file> has no addon.yml - skipped.`   | The jar isn't a SamsSeasons addon (maybe a normal plugin in the wrong folder).         |
| `Could not enable addon <name>: ...`         | The addon doesn't match your SamsSeasons version. Update both to the latest release.   |
| `/seasons editor` says the editor is missing | The editor jar isn't in `plugins/SamsSeasons/addons/`, or the server wasn't restarted. |

***

## Making Your Own

Developers can write addons too: a jar with an `addon.yml` (`name`, `version`, `main`) whose main class implements `SamsSeasonsAddon`. See the Developer API.
