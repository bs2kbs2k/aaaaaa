# set level

Set the output value of an analog pin as a percentage of total output. The brightness of the LED for that pin is set at the same percentage.

```sig
lights.setLevel(AnalogPin.A0, 100)
```

Both the output voltage and the LED brightness are set to a percentage of the total possible. So, if the maximum output voltage is +3V, then this will make +1.5V and half LED brightness at pin `A1`:

```block
lights.setLevel(AnalogPin.A1, 50)
```

## 매개 변수

* **name**: the analog pin with the LED you what to set a output perecentage for.
* **value**: a [number](/types/number) that is between `0` and `100` that is a percentage of the total output value.

## 예시

Set the analog pin value on `A0` from `0` to `100` percent in ten steps. The LED brightness increases for each step.

```blocks
for (let i = 0; i <= 10; i++) {
    lights.setLevel(AnalogPin.A0, i * 10)
    loops.pause(1000)
}
```

## 참고 항목

[set](/reference/lights/set)