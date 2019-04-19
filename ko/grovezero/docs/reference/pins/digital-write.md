# digital Write

Write a value of `false` or `true` to a digital pin.

```sig
pins.D0.digitalWrite(false)
```

Digital pins write one of two values: `false` or `true`. Often the `false` means something connected to the pin is turned **off** or its status is `false`. In a similar way, `true` means something connected to the pin is **on** or has a status of `true`.

The value from the last `||digital write||` stays at the pin until another `||digital write||` happens.

## 매개 변수

* **value**: a [boolean](types/boolean) value that is either `false` or `true`. The meaning of the value depends on how something connected to the pin behaves when it gets the new value.

## 예시

Light an LED on your bread board that is connected to pin `D4`. You write the value `true` to the pin.

```blocks
pins.D0.digitalWrite(true)
```

## 참고 항목

[`||digital read||`](/reference/pins/digital-read)