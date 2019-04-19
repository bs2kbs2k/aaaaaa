# light Level

Get the ambient illuminance from the [Light Sensor](https://www.seeedstudio.com/edu/grove-zero.html "Grove Zero Light Sensor") sensor in lux.

```sig
sensor.lightLevel()
```

Illuminance is the amount of visible light present. The Light Sensor measures this in units of [**lux**](https://wikipedia.org/wiki/Lux).

## 리턴값

* a [number](/types/number) that is the amount of lux measured by the Light Sensor.

## 예시

Every 5 seconds, see how much lux of illuminance there is. Display the value on the LED Matrix.

```blocks
loops.forever(function () {
    display.showNumber(sensor.lightLevel())
    loops.pause(5000)
})
```

## 참고 항목

[`||on light||`](/reference/sensor/on-light) [`||was light triggered||`](/reference/sensor/was-light-triggered)