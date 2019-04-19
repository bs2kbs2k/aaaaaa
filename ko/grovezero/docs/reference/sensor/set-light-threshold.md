# set Light Threshold

Say how much light will cause a `light` or `dark` event to happen.

```sig
sensor.setLightThreshold(LightEvent.Dark, 0)
```

The amount of light detected by the Light Sensor has a value between `0` and `3000`. This is a lux value.

If you want a darkness to mean any light value less than `100`, you set it like this:

```block
sensor.setLightThreshold(LightEvent.Dark, 100)
```

To have the `light` event happen when the light lux is more than `1200`, you can do this:

```block
sensor.setLightThreshold(LightEvent.Light, 1200)
```

## 매개 변수

* **type**: the light event to set the amount of light for. Either `dark` or `light`.
* **value**: the amount of light lux that triggers the light event.

## 예시

Make a `dark` event happen when the light lux level reaches `250` or less.

```blocks
sensor.setLightThreshold(LightEvent.Dark, 250)

sensor.onLight(LightEvent.Dark, () => {
    display.showString("It's dark when lux is 250")
})
```

## 참고 항목

[LED 스크린 빛 센서](/reference/sensor/light-level)