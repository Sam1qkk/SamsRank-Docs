---
description: Hook into SamsSeasons from your own plugin!
icon: rectangle-api
---

# Developer API

## Developer API

SamsSeasons has a small static API and Bukkit events. Add SamsSeasons as a soft dependency and compile against the jar.

```yaml
# paper-plugin.yml
dependencies:
  server:
    SamsSeasons:
      load: BEFORE
      required: false
```

### `SamsSeasonsAPI`

```java
import com.samscreations.samsseasons.api.SamsSeasonsAPI;

if (SamsSeasonsAPI.isReady() && SamsSeasonsAPI.hasSeasons(world)) {
    Season season = SamsSeasonsAPI.getSeason(world);          // SPRING, SUMMER, AUTUMN, WINTER
    SeasonPhase phase = SamsSeasonsAPI.getPhase(world);        // EARLY, MID, LATE
    SeasonSnapshot snap = SamsSeasonsAPI.getSnapshot(world);   // day, days, progress, remaining...
}
```

| Method                                             | Description                                                                                           |
| -------------------------------------------------- | ----------------------------------------------------------------------------------------------------- |
| `isReady()`                                        | SamsSeasons is enabled                                                                                |
| `hasSeasons(World)`                                | The world has seasons                                                                                 |
| `getSeason(World)` / `getPhase(World)`             | The current season and phase                                                                          |
| `getSnapshot(World)`                               | Everything about the current season at once                                                           |
| `setSeason(World, Season, SeasonPhase)`            | Change the season (phase may be null). False if the world has no seasons or follows the real calendar |
| `getTemperature(Player)`                           | The player's felt temperature in °C (null if off)                                                     |
| `addTemperatureModifier(Player, degrees, seconds)` | Warm or cool a player for a while                                                                     |
| `clearTemperatureModifiers(Player)`                | Remove those modifiers                                                                                |
| `getFestival(World)`                               | The running festival's id, or null                                                                    |
| `getForecast(World)`                               | The planned weather, today first: `CLEAR`, `RAIN`, `SNOW`, `STORM` or `SNOWSTORM`                     |

***

## Events

All in `com.samscreations.samsseasons.api.event`:

| Event                    | When                                                                                                 |
| ------------------------ | ---------------------------------------------------------------------------------------------------- |
| `SeasonChangeEvent`      | A world enters a new season. `getFrom()`, `getTo()`, `getCause()` (`NATURAL`, `SET`, `SKIP`, `SYNC`) |
| `SeasonPhaseChangeEvent` | Early → mid → late. `getSeason()`, `getFrom()`, `getTo()`                                            |
| `SeasonDayChangeEvent`   | A new day of the season. `getDay()`, `getDays()`                                                     |
| `FestivalEvent`          | A festival starts or ends. `getId()`, `getName()`, `isStart()`                                       |

```java
@EventHandler
public void onSeason(SeasonChangeEvent event) {
    if (event.getTo() == Season.WINTER) {
        Bukkit.broadcast(Component.text("Winter has come to " + event.getWorld().getName()));
    }
}
```

***

## Addons

Addon jars go into `plugins/SamsSeasons/addons/` and need an `addon.yml` (`name`, `version`, `main`). The main class implements `com.samscreations.samsseasons.addon.SamsSeasonsAddon` (`enable(SamsSeasons)`, `reload()`, `disable()`). The in-game editor is built this way.
