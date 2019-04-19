# sound Level

Get the noise level from the [Sound Sensor](https://www.seeedstudio.com/edu/grove-zero.html "Grove Zero Sound Sensor").

```sig
sensor.soundLevel()
```

The noise level detected by the Sound Sensor is a [number](/types) from `0` to `1023`. Totally quiet is `0` and extremely loud is `1023`.

## 리턴값

* a [number](/types/number) that is the amount of noise detected.

## 예시

Every 5 seconds, check how much noise there is. Display the value on the LED Matrix.

```blocks
loops.forever(function () {
    display.showNumber(sensor.soundLevel())
    loops.pause(5000)
})
```

## 참고 항목

[`||on loud sound||`](/reference/sensor/on-loud-sound) [`||was loud sound triggered||`](/reference/sensor/was-loud-sound-triggered)