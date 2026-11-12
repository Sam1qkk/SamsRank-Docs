---
description: Here you can learn how BlueMap and Dynmap support works!
icon: map
---

# BlueMap & Dynmap

## BlueMap & Dynmap

Web maps render what is in your world. Without help, they would draw the seasonal winter snow into their tiles, and it would stay on the map all year.

***

### Pause While Snow Lies

```yaml
integrations:
  maps:
    pause-while-snow: true
    bluemap:
      enabled: true
      maps: [world]      # the BlueMap map ids to pause
    dynmap:
      enabled: true
```

While seasonal snow lies in a world, SamsSeasons pauses the map's rendering. Once the snow has melted it resumes, so the map shows your world without the seasonal snow.
