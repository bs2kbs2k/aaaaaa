# 다음 이벤트가 발생하면 실행

Run some code when a touch sensor is pressed, bumped, or released.

```sig
sensors.touch1.onEvent(ButtonEvent.Bumped, function () {

});
```

## 매개 변수

* **ev**: the touch sensor action to run some code for. The touch actions (events) are: > * `pressed`: the sensor was pressed, or pressed and released > * `bumped`: the sensor was just bumped > * `released`: the sensor was just released
* **body**: the code you want to run when something happens to the touch sensor.

## 예시

Check for an event on touch sensor `touch 1`. Put an expression on the screen when the sensor is released.

```blocks
sensors.touch1.onEvent(ButtonEvent.Released, function () {
    brick.showImage(images.expressionsSick)
})
```

### 참고 항목

[is pressed](/reference/sensors/touch-sensor/is-pressed), [was pressed](/reference/sensors/touch-sensor/was-pressed), [pause until](/reference/sensors/touch-sensor/pause-until)