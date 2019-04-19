# temperature

Get the temperature value from [Temperature Sensor](https://www.seeedstudio.com/edu/grove-zero.html "Grove Zero Temperature Sensor") in degrees Celsius (°C).

```sig
sensor.temperature(TemperatureUnit.Celsius)
```

## 매개 변수

* unit, Celsius or Fahrenheit of the returned temperature

## 리턴값

* a [number](/types/number) that is the temperature in degrees Celsius (°C) measured by the Temperature Sensor.

## 예시

Check what the temperature is every minute. Show the temperature value on the LED Matrix.

```blocks
loops.forever(function () {
    display.showNumber(sensor.temperature())
    loops.pause(60000)
})
```

## 참고 항목

[`||on temperature||`](/reference/sensor/on-temperature) [`||is temperature event||`](/reference/sensor/was-temperature-triggered)