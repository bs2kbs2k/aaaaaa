# show Number

Show a number on the LED Matrix.

```sig
display.showNumber(0)
```

If you show a number greater than 9 or less than 0, it will scroll on the LED Matrix. This happens because those numbers have more than one *digit*.

## Parameters

* **num**: the [number](/types/number) value to display.

## Example

Find out what the temperature is from the temperature sensor every 10 seconds. Display the temperature value on the LEDs.

```blocks
loops.forever(function () {
    display.showNumber(sensor.temperature())
    loops.pause(10000)
})
```

## See also

[`||show string||`](/reference/display/show-string) [`||show icon||`](/reference/display/show-icon)