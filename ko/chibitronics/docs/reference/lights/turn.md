# turn

Turn a digital pin on or off.

```sig
lights.turn(DigitalPin.D0, 1)
```

## 매개 변수

* **name**: the digital pin that you what on or off.
* **value**: a [number](/types/number) that is either `1` for on or `0` for off.

## 예시

Toggle the LEDs on pins `D0` and `D5` forever.

```blocks
loops.forever(function () {
    lights.turn(DigitalPin.D0, 1)
    lights.turn(DigitalPin.D5, 0)
    loops.pause(500)
    lights.turn(DigitalPin.D0, 0)
    lights.turn(DigitalPin.D5, 1)
    loops.pause(500)
})
```

## 참고 항목

[set](/reference/lights/set)