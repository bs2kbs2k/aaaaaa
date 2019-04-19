# wait Micros

Make the part of the program running right now wait for some number of microseconds.

```sig
control.waitMicros(10)
```

The code inside the current block, such as a `||on start||`, `||run in background||`, and `||on event||` , waits for some amount of time. The time number is in microseconds (one-millionth of a second).

## 매개 변수

* **micros**: the [number](/types/number) of microseconds that this block of code to wait for.

## 예시

Turn on an a sensor that has a control command address of `23` on the i2c bus. Wait `20` microseconds for the sensor to detect something, then read the sensor value at address `24`.

```blocks
pins.i2cWriteNumber(23, 1, NumberFormat.UInt16LE, false)
pins.D0.digitalWrite(true)
control.waitMicros(20)
let temperature = pins.i2cReadNumber(24, NumberFormat.Int8LE, false)
```