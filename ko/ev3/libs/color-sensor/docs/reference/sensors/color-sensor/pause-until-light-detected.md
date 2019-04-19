# pause Until Light Condition Detected

Wait until a particular light condition is detected.

```sig
sensors.color1.pauseUntilLightDetected(LightIntensityMode.Reflected, Light.Dark)
```

You can wait for a change in either *ambient* or *reflected* light. This event happens when the sensor detects light going to `dark` or to `bright`. You choose what condition you will wait for.

## 매개 변수

* **mode**: lighting mode to use for detection. This is for either `ambient` or `reflected` light.
* **condition**: the condition that the light changed to: `dark` or `bright`.

## 예시

Wait for the ambient light to go dark, then show an expression on the screen.

```blocks
brick.showString("Waiting for dark", 1)
sensors.color1.pauseUntilLightDetected(LightIntensityMode.Reflected, Light.Dark)
brick.clearScreen()
brick.showImage(images.expressionsSick)
```

## 참고 항목

[on light detected](/reference/sensors/color-sensor/on-light-detected)