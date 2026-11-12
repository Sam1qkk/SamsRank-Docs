---
description: >-
  Festivals are special days of the calendar. They live in
  gameplay/festivals.yml.
icon: party-horn
---

# Festivals

## Festivals

Festivals are special days. They live in `gameplay/festivals.yml`.

***

## How It Works?

Every few seconds SamsSeasons checks each season world for a festival that should be running:

1. **It starts.** When its day comes (and its start `time`, if set), the festival is announced with a title and a chat message, a boss bar appears, and its `start-commands` run.
2. **It lasts.** For `length` days the boss bar fills up with its progress, and players in that world get the festival's **perks**. Players who join during it get them too.
3. **It ends.** After its last day, the boss bar disappears and the `end-commands` run.

Only one festival runs in a world at a time; a real-date holiday wins over a seasonal festival on the same day. `/seasons forecast`, the season menu and the calendar show what's coming, and `%samsseasons_festival_next%` counts down to it.

***

### Two Kinds

```yaml
festivals:
  harvest-festival:
    name: "&#E8A632Harvest Festival"
    season: autumn
    day: 4            # the 4th day of autumn
    length: 2
  christmas:
    name: "&#D94B4BChristmas"
    date: "12-24"     # a real-world date (MM-DD), or "easter"
    length: 3
    time: morning
```

* **Seasonal festivals** (`season` + `day`) start on a day of an in-game season. On a server where a season lasts 8 days, the Harvest Festival is on the 4th day of every autumn.
* **Holidays** (`date`) follow the **real** date: Christmas starts on 24 December in real life, whatever the in-game season is. `easter` is calculated for every year.

***

## Start Time

On its first day, a festival can wait for a time of day:

| `time`          | Starts at                 |
| --------------- | ------------------------- |
| `any` (default) | As soon as the day begins |
| `morning`       | Sunrise                   |
| `noon`          | Midday                    |
| `evening`       | Sunset                    |
| `night`         | Nightfall                 |

Out of the box Halloween starts in the evening, Christmas in the morning and New Year at night.

***

## Perks

While a festival runs, players in that world can get:

* `effects`: potion effects (e.g. speed, luck)
* `xp-multiplier`: more experience from everything
* `particles`: festive particles around players
* `fireworks`: harmless fireworks in the sky now and then
* `warmth`: degrees added to everyone's temperature (perfect for winter festivals)
* `clear-weather`: no rain while it lasts
* `rewards`: commands run **once per player** per festival (e.g. a crate key), also for players who join later
* `icon`: the item shown in the season menu and the calendar

***

## Commands

`start-commands` and `end-commands` run from the console when the festival begins and ends. Use `%world%`, and `%player%` to run a command once for every player in that world:

```yaml
start-commands:
  - "broadcast The Harvest Festival has begun in %world%!"
  - "crate key give %player% harvest 1"
```

***

## Default Festivals

| Festival         | When          | Length | Starts            |
| ---------------- | ------------- | ------ | ----------------- |
| Blossom Festival | Spring, day 3 | 1 day  | as the day begins |
| Midsummer        | Summer, day 4 | 1 day  | as the day begins |
| Harvest Festival | Autumn, day 4 | 2 days | as the day begins |
| Frost Fair       | Winter, day 5 | 1 day  | as the day begins |
| Halloween        | 31 October    | 1 day  | evening           |
| Christmas        | 24 December   | 3 days | morning           |
| New Year         | 31 December   | 2 days | night             |
| Easter           | Easter Sunday | 2 days | as the day begins |

***

## Admin Control

* `/seasons festival list` shows every festival and when it comes.
* `/seasons festival start <festival> [world]` starts one now (it runs for its full length).
* `/seasons festival stop [festival] [world]` ends the running one. A natural festival stopped early won't restart until its next date.
