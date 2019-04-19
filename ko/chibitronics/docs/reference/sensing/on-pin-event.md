# on Pin Event

Run some code when something happens at a pin.

```sig
sensing.onPinEvent(DigitalPin.D0, PinEvent.Pressed, function () {

})
```

## 매개 변수

* **name**: the name of the pin to watch for an event at.
* **ev**: the pin event to run some code for. The pin events are: > * `pressed`: the pin was pressed (touched). > * `released`: the pin was released (finger lifted off). > * `changed`: the condition at the pin has changed. > * `HIGH`: a high voltage input signal is detected on the pin. > * `LOW`: a low voltage input signal is detected on the pin.
* **body**: the code you want to run when something happens at the pin.

## 예시

Flash each of the LEDs to the right when pin `D0` is pressed. Then, flash the LEDs back to the left when pin `D0` is released.

```blocks
sensing.onPinEvent(DigitalPin.D0, PinEvent.Pressed, function () {
    for (let i = 0; i <= 5; i++) {
        lights.set(i, 1)
        loops.pause(30)
        lights.set(i, 0)
    }
})
sensing.onPinEvent(DigitalPin.D0, PinEvent.Released, function () {
    for (let i = 0; i <= 5; i++) {
        lights.set(5 - i, 1)
        loops.pause(30)
        lights.set(5 - i, 0)
    }
})
```

## 참고 항목

[pressed](/reference/sensing/pressed)