# set Sound Threshold

Say how much sound will cause a `quiet` or `loud` event to happen.

```sig
sensor.setSoundThreshold(0)
```

The value for how loud it is goes from `0` to `1023`. No noise at all is `0` and when it is extremely noisy, the value is `1023`.

If you want quiet to mean that the sound level is `200` or less, you set it like this:

```block
sensor.setSoundThreshold(200)
```

To have the `loud` event mean that the sound level is at `900` or above, you can do this:

```block
sensor.setSoundThreshold(1200)
```

## 매개 변수

* **type**: the sound event to set the loudness level for. Either `quiet` or `loud`.
* **value**: the amount of loudness that triggers the sound event. This is a [number](/types/number) between `0` and `1023`.

## 예시

Make the `loud` event happen when the Sound Sensor detects a sound level of `800`.

```blocks
sensor.setSoundThreshold(800)

sensor.onLoudSound(() => {
    display.showString("It's really getting loud!")
})
```

## 참고 항목

[get sound value](/reference/sensor/sound-level)