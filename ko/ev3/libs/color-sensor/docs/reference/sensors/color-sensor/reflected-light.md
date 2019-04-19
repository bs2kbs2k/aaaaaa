# reflected Light

Get the amount of reflected light dectected.

```sig
sensors.color1.reflectedLight()
```

The amount of reflected light measured is in the range of `0` (darkest) to `100` (brightest).

## 리턴값

* a [number](/types/number) that is the amount of ambiernt light measured. No light (darkness) is `0` and the brightest light is `100`.

## 예시

Make the status light show `green` if the reflected light is greater than `20`.

```blocks
forever(function () {
    if (sensors.color1.reflectedLight() > 20) {
        brick.setStatusLight(StatusLight.Green)
    } else {
        brick.setStatusLight(StatusLight.Orange)
    }
})
```

## 참고 항목

[ambient light](/reference/sensors/color-sensor/ambient-light)