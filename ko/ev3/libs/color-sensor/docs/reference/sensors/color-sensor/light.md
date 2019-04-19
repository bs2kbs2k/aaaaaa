# light

Get the amount of ambient or reflected light measured by the sensor.

```sig
sensors.color1.light(LightIntensityMode.Ambient)
```

The light sensor adjusts itself to more accurately measure light depending on the source of the light. You decide if you want to measure *ambient* light (light all around or direct light) or if you want to know how much light is reflected from a surface. The amount of light measured is in the range of `0` (darkest) to `100` (brightest).

## 매개 변수

* **mode**: the type of measurement for light. This is either `ambient` or `reflected` light.

## 리턴값

* a number that is the amount of light measured. No light (darkness) is `0` and the brightest light is `100`.

## 예시

Make the status light show `green` if the ambient light is greater than `20`.

```blocks
forever(function () {
    if (sensors.color1.light(LightIntensityMode.Ambient) > 20) {
        brick.setStatusLight(StatusLight.Green)
    } else {
        brick.setStatusLight(StatusLight.Orange)
    }
})
```

## 참고 항목

[calibrate light](/reference/sensors/color-sensor/calibrate-light)