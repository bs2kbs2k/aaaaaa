# set Weather

Change the current weather.

```sig
gameplay.setWeather(Weather.Clear);
```

## Parameters

* **weather**: the desired weather, like: *Weather.Clear* > * `clear`: sunny, no rain or storms > * `rain`: rainy, no sun > * `thunder`: thunderstorm, lot's of rain

## Example

Bring on a thunderstorm with just a command.

```blocks
player.onChat("storm", function {
    gameplay.setWeather(Weather.Thunder)
});
```