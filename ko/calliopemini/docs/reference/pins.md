# 핀

디지털/아날로그 신호, 서보, I2C ... 에서 사용되는 핀의 전류를 제어합니다.

```cards
pins.digitalReadPin(DigitalPin.P0);
pins.digitalWritePin(DigitalPin.P0, 0);
pins.analogReadPin(AnalogPin.P1);
pins.analogWritePin(AnalogPin.P1, 1023);
pins.analogSetPeriod(AnalogPin.P1, 20000);
pins.map(0, 0, 1023, 0, 4);
pins.onPulsed(DigitalPin.P0, PulseValue.High, () => {

});
pins.pulseDuration();
pins.pulseIn(DigitalPin.P0, PulseValue.High);
pins.servoWritePin(AnalogPin.P1, 180);
pins.servoSetPulse(AnalogPin.P1, 1500);
pins.i2cReadNumber(0, NumberFormat.Int8LE);
pins.i2cWriteNumber(0, 0, NumberFormat.Int8LE);
pins.spiWrite(0);
pins.setPull(DigitalPin.P0, PinPullMode.PullDown);
pins.analogPitch(0, 0);
pins.analogSetPitchPin(AnalogPin.P1);
```

### 참고 항목

[digitalReadPin](/reference/pins/digital-read-pin), [digitalWritePin](/reference/pins/digital-write-pin), [analogReadPin](/reference/pins/analog-read-pin), [analogWritePin](/reference/pins/analog-write-pin), [analogSetPeriod](/reference/pins/analog-set-period), [map](/reference/pins/map), [onPulsed](/reference/pins/on-pulsed), [pulseDuration](/reference/pins/pulse-duration), [pulseIn](/reference/pins/pulse-in), [servoWritePin](/reference/pins/servo-write-pin), [servoSetPulse](/reference/pins/servo-set-pulse), [i2cReadNumber](/reference/pins/i2c-read-number), [i2cWriteNumber](/reference/pins/i2c-write-number), [setPull](/reference/pins/set-pull), [analogPitch](/reference/pins/analog-pitch), [analogSetPitchPin](/reference/pins/analog-set-pitch-pin), [spiWrite](/reference/pins/spi-write)