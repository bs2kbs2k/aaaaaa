# set Weather

현재 날씨를 변경합니다.

```sig
gameplay.setWeather(Weather.Clear);
```

## 매개 변수

* **weather**: the desired weather, like: *Weather.Clear* > * `clear`: sunny, no rain or storms > * `rain`: rainy, no sun > * `thunder`: thunderstorm, lot's of rain

## 예시

Bring on a thunderstorm with just a command.

```blocks
player.onChat("storm", function {
    gameplay.setWeather(Weather.Thunder)
});
```