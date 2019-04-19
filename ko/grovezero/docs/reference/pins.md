# 핀

Use the pins for digital signals and i2c.

## Digital

```cards
pins.D0.digitalRead()
pins.D0.digitalWrite(false)
pins.D0.onPulsed(PulseValue.Low, () => {})
pins.D0.setPull(PinPullMode.PullDown)
pins.D0.pulseIn(PulseValue.High,0)
pins.pulseDuration()
```

## I2C

```cards
pins.i2cReadNumber(0, NumberFormat.Int8LE, false)
pins.i2cWriteNumber(
0,
0,
NumberFormat.Int8LE,
false
)
```

## 참고 항목

[digital read](/reference/pins/digital-read), [digital write](/reference/pins/digital-write), [on pulsed](/reference/pins/on-pulsed), [set pull](/reference/pins/set-pull), [pulse in](/reference/pins/pulse-in), [pulse duration](/reference/pins/pulse-duration), [i2c read number](/reference/pins/i2c-read-number), [i2c write number](/reference/pins/i2c-write-number)