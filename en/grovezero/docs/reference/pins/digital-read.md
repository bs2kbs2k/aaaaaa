# digital Read

Read a digital `false` or `true` from a pin.

```sig
pins.D0.digitalRead()
```

Digital pins read one of two values: `false` or `true`. Often the `false` means something connected to the pin is turned **off** or its status is `false`. In a similar way, `true` means something connected to the pin is **on** or has a status of `true`.

## Returns

* a [boolean](types/boolean) value that is either `false` or `true`. The meaning of the value depends on how something connected to the pin decides on what value to give.

## Example

See if a switch on your bread board is on or off. The switch is connected to pin `D0`. If the switch is on, show "ON" on the LED Matrix. If it's off, show "OFF".

```blocks
let mySwitchOn = pins.D0.digitalRead()
if (mySwitchOn) {
    display.showString("ON")
} else {
    display.showString("OFF")
}
```

## See Also

[`||digital write||`](/reference/pins/digital-write)