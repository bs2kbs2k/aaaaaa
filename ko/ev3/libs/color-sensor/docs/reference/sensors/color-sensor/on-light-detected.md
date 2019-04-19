# on Light Changed

Run some code when the amount of light dectected changes.

```sig
sensors.color1.onLightDetected(LightIntensityMode.Reflected, Light.Dark, function () {

})
```

You can check for a change in either *ambient* or *reflected* light and run some code when it happens. This event happens when the sensor detects light going to `dark` or to `bright`. You choose what condition you will run your code for.

## 매개 변수

* **mode**: lighting mode to use for detection. This is for either `ambient` or `reflected` light.
* **condition**: the condition that the light changed to: `dark` or `bright`.
* **handler**: the code you want to run when the light changes.

## 예시

Show a message on the screen when the ambient light goes dark.

```blocks
sensors.color1.onLightDetected(LightIntensityMode.Ambient, Light.Dark, function() {
    brick.clearScreen();
    brick.showString("It just got dark", 1)
    brick.showString("Can you see me?", 2)
})
```

## 참고 항목

[light](/reference/sensors/color-sensor/light), [on color detected](/reference/sensors/color-sensor/on-color-detected)