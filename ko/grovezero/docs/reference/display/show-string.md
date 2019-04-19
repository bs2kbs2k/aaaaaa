# show String

Show a text string on the LED Matrix.

```sig
display.showString("Hello")
```

Any text with more than one character will scroll across the LED Matrix one character at a time.

## 매개 변수

* **str**: a text [string](/types/string) you want to display on the LEDs.

## 예시

Display `"I am dizzy"` when the 9-Dof sensor detects a shaking motion. Show `"I feel cold"` when the temperature sensor detects that it's cold.

```blocks
sensor.onIMU(IMUEvent.FreeFall, function () {
    display.showString("I am dissy")
})

sensor.onTemperature(TemperatureEvent.Cold, function () {
    display.showString("I feel cold")
})
```

## 참고 항목

[`||show string||`](/reference/display/show-string) [`||show icon||`](/reference/display/show-icon)