# analog Read

Read an analog input value from a pin.

```sig
pins.analogRead(AnalogPin.A0)
```

Your board can read a number value for a *signal* on an analog pin. A signal is some amount of voltage measured by a circuit on your board. The value for that signal doesn't actually match its voltage, but it's a number that means how much signal is there. The number you read for the signal is something between `0` and `255`. A `0` is no signal and `255` is a full signal.

## 리턴값

* a [number](/types/number) between `0` and `255` that is amount of signal at the pin.

## 예시

Use the RGB LED as a signal meter. Read from pin `A2` and light the RBG LED with a color wheel value that relates to the signal value.

```blocks
loops.forever(function() {
    let signal = pins.analogRead(AnalogPin.A2)
    rgb.setColor(rgb.wheel(signal))
    loops.pause(1000)
}) 
```

## 참고 항목

[`||pins:analog write||`](/reference/pins/analog-write)