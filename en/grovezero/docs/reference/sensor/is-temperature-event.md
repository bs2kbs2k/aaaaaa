# is Temperature Event

Get the last [Temperature Sensor](https://www.seeedstudio.com/edu/grove-zero.html "Grove Zero Temperature Sensor") event and see if it detected a cold or hot environment.

```sig
sensor.isTemperatureEvent(TemperatureEvent.Cold)

```

## Parameters

* **event**: the temperature event you want to check for. You can check if the temperature is either `cold` or `hot`.

## Returns

* a [boolean](/types/boolean) value that is `true` if the temperature event happened, or `false` if not.

## Example

Show a smiley face when the sensor detects that it's `cold`. Otherwise, display a sad face.

```blocks
loops.forever(function () {
    if (sensor.isTemperatureEvent(TemperatureEvent.Cold)) {
        display.showIcon(IconType.Smile)
    } else {
        display.showIcon(IconType.Sad)
    }
})
```

## See also

[`||on temperature||`](/reference/sensor/on-temperature) [`||tempurature||`](/reference/sensor/temperature)