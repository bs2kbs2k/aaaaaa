# on Temperature

Do something when the [Temperature Sensor](https://www.seeedstudio.com/edu/grove-zero.html "Grove Zero Temperature Sensor") detects a hot or cold condition.

```sig
sensor.onTemperature(TemperatureEvent.Cold, function () {

})
```

## Parameters

* **event**: the temperature event you want to run some code for. This is either `hot` or `cold`.
* **handler**: the code to run when the temperature event happens.

## Example

Show a smile on the LED Matrix when the sensor detects cold. Display a sad face if it's hot.

```blocks
sensor.onTemperature(TemperatureEvent.Cold, function () {
    display.showIcon(IconType.Smile)
})
sensor.onTemperature(TemperatureEvent.Hot, function () {
    display.showIcon(IconType.Sad)
})
```

## See also

[`||was temperature triggered||`](/reference/sensor/was-temperature-triggered) [`||temperature||`](/reference/sensor/temperature)