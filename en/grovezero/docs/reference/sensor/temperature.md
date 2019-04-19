# temperature

Get the temperature value from [Temperature Sensor](https://www.seeedstudio.com/edu/grove-zero.html "Grove Zero Temperature Sensor") in degrees Celsius (°C).

```sig
sensor.temperature(TemperatureUnit.Celsius)
```

## Parameters

* unit, Celsius or Fahrenheit of the returned temperature

## Returns

* a [number](/types/number) that is the temperature in degrees Celsius (°C) measured by the Temperature Sensor.

## Example

Check what the temperature is every minute. Show the temperature value on the LED Matrix.

```blocks
loops.forever(function () {
    display.showNumber(sensor.temperature())
    loops.pause(60000)
})
```

## See also

[`||on temperature||`](/reference/sensor/on-temperature) [`||is temperature event||`](/reference/sensor/was-temperature-triggered)