---
description: List of all placeholders!
icon: percent
---

# Placeholders

## Placeholders

With [PlaceholderAPI](https://www.spigotmc.org/resources/placeholderapi.6245/) installed, these work everywhere (scoreboards, tab, chat...). They use the player's world.

***

### Season

| Placeholder                                       | Example               |
| ------------------------------------------------- | --------------------- |
| `%samsseasons_season%`                            | Coloured season name  |
| `%samsseasons_season_plain%`                      | `Autumn`              |
| `%samsseasons_season_id%`                         | `autumn`              |
| `%samsseasons_color%`                             | `#E8A632`             |
| `%samsseasons_phase%` / `_phase_id`               | `Late` / `late`       |
| `%samsseasons_progress%`                          | `77` (percent)        |
| `%samsseasons_progress_bar%`                      | Coloured progress bar |
| `%samsseasons_remaining%`                         | `36m 25s`             |
| `%samsseasons_remaining_seconds%`                 | `2185`                |
| `%samsseasons_day%` / `_days`                     | `7` / `8`             |
| `%samsseasons_next%` / `_next_plain` / `_next_id` | The next season       |
| `%samsseasons_paused%`                            | `true` / `false`      |
| `%samsseasons_state%`                             | Running / Paused      |

***

### Calendar

| Placeholder                  | Example                                                                                       |
| ---------------------------- | --------------------------------------------------------------------------------------------- |
| `%samsseasons_date%`         | `Tuesday, 2 November 1`                                                                       |
| `%samsseasons_weekday%`      | `Tuesday`                                                                                     |
| `%samsseasons_month%`        | `November`                                                                                    |
| `%samsseasons_day_of_month%` | `2`                                                                                           |
| `%samsseasons_year%`         | `1`                                                                                           |
| `%samsseasons_day_of_year%`  | `45` (day of the year; 1 = first day of spring, or the real day of the year in calendar mode) |

***

### Weather & Festivals

| Placeholder                                  | Example                              |
| -------------------------------------------- | ------------------------------------ |
| `%samsseasons_weather%`                      | Today's weather                      |
| `%samsseasons_forecast_1%` ... `_forecast_7` | Weather in N days                    |
| `%samsseasons_festival%`                     | The running festival (empty if none) |
| `%samsseasons_festival_next%`                | The next festival                    |
| `%samsseasons_festival_next_days%`           | Days until it starts                 |

***

### Temperature

| Placeholder                         | Example         |
| ----------------------------------- | --------------- |
| `%samsseasons_temperature%`         | `-3 °C`         |
| `%samsseasons_temperature_raw%`     | `-3.2`          |
| `%samsseasons_temperature_feeling%` | Coloured `Cold` |
| `%samsseasons_temperature_icon%`    | A coloured icon |
