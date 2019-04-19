# show Bars

Display a bar graph on the LED Matrix to show a positive value.

```sig
display.showBars(0, 1023)
```

This is a way to graph a number.

## 매개 변수

* **value**: a positive value to be graphed.
* **max**: the maximum value that can be graphed.

## 예시

Find out what the temperature is from the temperature sensor every 10 seconds. Display the temperature value as bar graph on the LED matrix.

```blocks
loops.forever(function () {
    display.showBars(sensor.temperature(), 80)
    loops.pause(10000)
})
```

## 참고 항목

[`||display number||`](/reference/display/show-number) [`||display icon||`](/reference/display/show-icon)