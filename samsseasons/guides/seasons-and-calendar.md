---
description: Here, you can learn how seasons and calendar works!
icon: calendar
---

# Seasons & Calendar

## The Four Seasons

The seasons live in `seasons.yml`. Each season is split into three equal phases (**early**, **mid** and **late**), and most features can be tuned per phase.

```yaml
spring:
  length: 8d          # d = day, h = hour, e.g. 3d12h
  transition: 1d      # how long the world blends into the next season
  color: "#9BD65B"    # used in messages, placeholders and menus
```

Season names and descriptions are translated, so they live in the language file (`season.<id>.name` / `description`).

***

### How the Clock Works?

Every world with seasons has a clock that SamsSeasons checks once a second. When the time of a season is up, the next one begins: players see the season banner (or a title), hear the season's sound and get a chat message, and everything that depends on the season switches over: colours, weather, crops, mobs, temperature and so on. Each season is split into three equal phases, early, mid and late, and the change from one phase to the next is announced with a short chat line.

A new season doesn't snap in. For the `transition` at the end of a season, the look of the world already blends towards the next one (first snow, leaves turning). The clock is saved regularly and on every change, so a restart never loses progress, and with `pause` the season simply stays where it is.

***

### Clock Modes

Set in `config.yml` under `worlds.default` (or per world in `worlds/<world>.yml`):

| `clock-mode` | How time moves forward                                                                                                            |
| ------------ | --------------------------------------------------------------------------------------------------------------------------------- |
| `game-days`  | In-game days. A "day" in `length` is one Minecraft day (20 minutes). Sleeping skips time too.                                     |
| `real-time`  | Real-world time. `7d` really is one week. With `count-offline: true` it keeps counting while the server is off.                   |
| `calendar`   | Follows the real calendar month (March to May is spring...). Set `hemisphere: south` to flip it. `set`/`next`/`pause` are locked. |

`start-season` decides where a brand-new world begins.

***

### The In-Game Calendar

Every day has a date: three months per season (spring = March, April, May), seven weekdays and a year that counts up each spring.

* `/seasons date` shows today, and `/seasons setdate 14 July` jumps there.
* `/calendar` opens the calendar menu: every day of the season, today, festivals, holidays and the coming weather.
* The date shows in `/seasons info`, the season menu and placeholders (`%samsseasons_date%`).
* Month and weekday names, and the date format, come from the language file (`calendar.*`).
* In `calendar` clock mode the real date is shown.

Turn it off with `calendar.enabled: false` in `seasons.yml` (or the **Calendar dates** switch in the editor). `calendar.start-year` sets the first year.

***

## Worlds

```yaml
worlds:
  enabled:
    - all
  disabled: []
  share-calendar: true
```

* **`all`**: every overworld-type world has seasons, including worlds that Multiverse or other plugins load later. The Nether and the End stay vanilla unless you list them by name.
* **`disabled`**: worlds left out of `all`, e.g. a lobby or an arena.
* **`share-calendar`**: every extra world follows the main world's calendar, so the whole server has one season. Set `false` to give each world its own clock.

You can also switch a world off in-game: `/seasons disable [world]` adds it to `disabled`, and `/seasons enable [world]` takes it out again. The world keeps its date and continues where it was, and seasonal snow and plants in a disabled world melt and wither away by themselves.

Worlds can be written by name (`world`) or by key (`minecraft:overworld`). On Paper 26.1+, where worlds live under `world/dimensions/`, keys are the safer choice.

***

### Per-World Settings

Create `plugins/SamsSeasons/worlds/<world>.yml` (see the generated `worlds/example.yml`). Any key set there overrides `worlds.default` for that world only, e.g. a real-time survival world next to a game-days event world. Use `link-to: world` to make one world share another's calendar.
