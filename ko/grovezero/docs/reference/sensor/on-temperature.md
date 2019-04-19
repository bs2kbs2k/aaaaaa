# on Temperature

Do something when the [Temperature Sensor](https://www.seeedstudio.com/edu/grove-zero.html "Grove Zero Temperature Sensor") detects a hot or cold condition.

```sig
sensor.onTemperature(TemperatureEvent.Cold, function () {

})
```

## 매개 변수

* **event**: the temperature event you want to run some code for. This is either `hot` or `cold`.
* **이벤트 핸들러**: 온도 관련 이벤트가 발생했을 때 실행시킬 코드.

## 예시

Show a smile on the LED Matrix when the sensor detects cold. Display a sad face if it's hot.

```blocks
sensor.onTemperature(TemperatureEvent.Cold, function () {
    display.showIcon(IconType.Smile)
})
sensor.onTemperature(TemperatureEvent.Hot, function () {
    display.showIcon(IconType.Sad)
})
```

## 참고 항목

[`||was temperature triggered||`](/reference/sensor/was-temperature-triggered) [`||temperature||`](/reference/sensor/temperature)