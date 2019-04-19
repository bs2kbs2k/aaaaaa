# 핀

디지털/아날로그 신호, 서보, I2C ... 에서 사용되는 핀의 전류를 제어합니다.

```cards
pins.digitalReadPin(DigitalPin.P0);
pins.digitalWritePin(DigitalPin.P0, 0);
pins.analogReadPin(AnalogPin.P0);
pins.analogWritePin(AnalogPin.P0, 1023);
pins.analogSetPeriod(AnalogPin.P0, 20000);
pins.map(0, 0, 1023, 0, 4);
pins.onPulsed(DigitalPin.P0, PulseValue.High, () => {

});
pins.pulseDuration();
pins.pulseIn(DigitalPin.P0, PulseValue.High);
pins.setPull(DigitalPin.P0, PinPullMode.PullDown);
pins.analogPitch(0, 0);
pins.analogSetPitchPin(AnalogPin.P0);
```

## 서보

```cards
pins.servoWritePin(AnalogPin.P0, 180);
pins.servoSetPulse(AnalogPin.P0, 1500);
```

## I2C

```cards
pins.i2cReadNumber(0, NumberFormat.Int8LE);
pins.i2cWriteNumber(0, 0, NumberFormat.Int8LE);
```

## SPI

```cards
pins.spiWrite(0);
pins.spiFrequency(1000000);
pins.spiFormat(8,3);
pins.spiPins(DigitalPin.P0, DigitalPin.P1, DigitalPin.P2);
```

## 참고 항목

[디지털 입력](/reference/pins/digital-read-pin), [디지털 출력](/reference/pins/digital-write-pin), [아날로그 입력](/reference/pins/analog-read-pin), [아날로그 출력](/reference/pins/analog-write-pin), [아날로그 PWM 설정 주기](/reference/pins/analog-set-period), [값 변환(map)](/reference/pins/map), [펄스 감지하면 실행](/reference/pins/on-pulsed), [펄스 주기(µs)](/reference/pins/pulse-duration), [펄스 입력(µs)](/reference/pins/pulse-in), [서보 출력](/reference/pins/servo-write-pin), [서보 펄스 설정](/reference/pins/servo-set-pulse), [I2C통신 입력](/reference/pins/i2c-read-number), [I2C통신 출력](/reference/pins/i2c-write-number), [핀 풀(pull) 설정](/reference/pins/set-pull), [PWM 출력](/reference/pins/analog-pitch), [아날로그 출력 설정](/reference/pins/analog-set-pitch-pin), [SPI통신 전송](/reference/pins/spi-write), [SPI통신 핀 설정](/reference/pins/spi-pins),[SPI통신 포맷 설정](/reference/pins/spi-format),[SPI통신 주파수 설정](/reference/pins/spi-frequency)