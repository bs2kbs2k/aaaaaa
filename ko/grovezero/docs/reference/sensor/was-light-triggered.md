# was Light triggered

Get the last [Light Sensor](https://www.seeedstudio.com/edu/grove-zero.html "Grove Zero Light Sensor") event and see if it was either `dark` or `light`.

```sig
sensor.wasLightTriggered(LightEvent.Light)
```

## 매개 변수

* **event**: the light event you want to check for. You can check if the light condition is either `dark` or `light`.

## 리턴값

* a [boolean](/types/boolean) value that is `true` if the light event happened, or `false` if not.

## 예시

Make the LED Matrix show a smiley face when the sensor is in a `light` environment. Otherwise, show a sad face.

```blocks
loops.forever(function () {
    if (sensor.wasLightTriggered(LightEvent.Light)) {
        display.showIcon(IconType.Smile)
    } else {
        display.showIcon(IconType.Sad)
    }
})
```

## 참고 항목

[`||light level||`](/reference/sensor/light-level) [`||on light||`](/reference/sensor/on-light)