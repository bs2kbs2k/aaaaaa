# set Temperature Threshold

Say how much heat will cause the `cold` or `hot` event to happen.

```sig
sensor.setTemperatureThreshold(TemperatureEvent.Cold, 0, TemperatureUnit.Celsius)
```

The temperature values you set for an event are between `5` and `50`. The value is in degrees Celsius.

If you want cold to mean that the temperature is `10` or less, you set it like this:

```block
sensor.setTemperatureThreshold(TemperatureEvent.Cold, 10, TemperatureUnit.Celsius)
```

For the `hot` event, if you want hot to mean any temperature at or above `30`, you can do this:

```block
sensor.setTemperatureThreshold(TemperatureEvent.Hot, 30, TemperatureUnit.Celsius)
```

## Parameters

* **type**: the temperature event to set the degree value for. Either `cold` or `hot`.
* **value**: the temperature in degrees Celsius that causes the temperature event. This is a [number](/types/number) between `5` and `50`.

## Example

Set the cold temperature threshold to `10` degrees. When it gets to `10` degrees Celsius, tell the world that it's getting cold.

```blocks
sensor.setTemperatureThreshold(TemperatureEvent.Cold, 10, TemperatureUnit.Celsius)

sensor.onTemperature(TemperatureEvent.Cold, () => {
    display.showString("It's cold now, burr!")
})
```

## See also

[temperature](/reference/sensor/temperature)