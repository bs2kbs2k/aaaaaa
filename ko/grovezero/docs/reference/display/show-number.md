# 정수 출력

LED 매트릭스에 정수를 출력하세요.

```sig
display.showNumber(0)
```

If you show a number greater than 9 or less than 0, it will scroll on the LED Matrix. This happens because those numbers have more than one *digit*.

## 매개 변수

* **num**: the [number](/types/number) value to display.

## 예시

Find out what the temperature is from the temperature sensor every 10 seconds. Display the temperature value on the LEDs.

```blocks
loops.forever(function () {
    display.showNumber(sensor.temperature())
    loops.pause(10000)
})
```

## 참고 항목

[`||show string||`](/reference/display/show-string) [`||show icon||`](/reference/display/show-icon)