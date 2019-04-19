# threshold

Get the threshold value for dark or bright light.

```sig
sensors.color1.threshold(Light.Dark)
```

Light intensity is measured from `0` (very dark) to `100` (very bright). A *threshold* sets what dark and bright mean for your purposes. A threshold is a boundary or a limit. If a light intensity of `20` means that it's dark, then the sensor threshold for `dark` is `20`. Also, if `75` means bright, then the threshold value for `bright` is `75`.

## 리턴값

* a [number](/types/number) that is the amount of light set for the threshold. No light (darkness) is `0` and the brightest light is `100`.

## 예시

Find out what light level is set as the `dark` threshold when a dark light event happens.

```blocks
sensors.color3.onLightDetected(LightIntensityMode.Reflected, Light.Dark, function () {
    brick.showValue("DarknessThresholdValue", sensors.color3.threshold(Light.Dark), 1)
})
```

## 참고 항목

[set threshold](/reference/sensors/color-sensor/set-threshold)