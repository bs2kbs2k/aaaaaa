# set Threshold

Set the threshold value for dark or bright light.

```sig
sensors.color1.setThreshold(Light.Dark, 0)
```

Light intensity is measured from `0` (very dark) to `100` (very bright). You can decide what dark and bright mean for your purposes and set a *threshold* for them. A threshold is a boundary or a limit. If you want a light intensity of `20` mean that it's dark, then you set the sensor threshold for `dark` to `20`. Also, if you think that `75` is bright, then you can set the threshold for `bright` to that.

After setting a threshold, any event for that light condition won't happen until the amount of light reaches your threshold value:

```block
sensors.color1.setThreshold(Light.Dark, 20)
sensors.color1.onLightDetected(LightIntensityMode.Reflected, Light.Dark, function () {
    brick.showMood(moods.sleeping)
})
```

## 매개 변수

* **condition**: the light intensity threshold to set, `dark` or `bright`.
* **value**: the value of light intensity for the threshold: `0` for very dark to `100` for very bright.

## 예시

Make a daylight alarm. When the ambient light reaches `70` flash the status light and play a sound.

```blocks
sensors.color3.setThreshold(Light.Bright, 70)
sensors.color3.onLightDetected(LightIntensityMode.Ambient, Light.Bright, function () {
    brick.setStatusLight(StatusLight.GreenFlash)
    for (let i = 0; i < 5; i++) {
        music.playSoundEffectUntilDone(sounds.mechanicalBackingAlert)
    }
})
```

## 참고 항목

[threshold](/reference/sensors/color-sensor/threshold)