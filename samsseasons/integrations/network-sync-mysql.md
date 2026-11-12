---
description: Here you can learn how MySQL support works!
icon: database
---

# Network Sync (MySQL)

## Network Sync (MySQL)

Running a network? Let every server share one season and one date.

***

## Setup

On **every** server, in `config.yml`:

```yaml
storage:
  type: mysql
  mysql:
    host: localhost
    port: 3306
    database: minecraft
    # username / password ...
  sync:
    enabled: true
    role: main        # exactly ONE server is main, the rest are follower
    interval: 10      # seconds between checks on followers
```

* The **main** server runs the seasons and shares them.
* **Followers** copy the season, phase and date from the database. `/seasons set`, `next`, `pause` and `resume` are refused there: change the season on the main server.

Everything else (snow, particles, temperature...) runs locally on each server, following the shared season.

{% hint style="info" %}
A single server doesn't need any of this: the default `type: sqlite` stores everything in a local file.
{% endhint %}
