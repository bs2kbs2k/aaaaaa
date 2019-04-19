# was Temperature triggered

Get the last [Temperature Sensor](https://www.seeedstudio.com/edu/grove-zero.html "Grove Zero Temperature Sensor") event and see if it detected a cold or hot environment.

```sig
sensor.wasTemperatureTriggered(TemperatureEvent.Cold)

```

## 매개 변수

* **event**: the temperature event you want to check for. You can check if the temperature is either `cold` or `hot`.

## 리턴값

* a [boolean](/types/boolean) value that is `true` if the temperature event happened, or `false` if not.

## 예시

Show a smiley face when the sensor detects that it's `cold`. Otherwise, display a sad face.

```blocks
loops.forever(function () {
    if (sensor.wasTemperatureTriggered(TemperatureEvent.Cold)) {
        display.showIcon(IconType.Smile)
    } else {
        display.showIcon(IconType.Sad)
    }
})
```

## 참고 항목

[`||on temperature||`](/reference/sensor/on-temperature) [`||tempurature||`](/reference/sensor/temperature)