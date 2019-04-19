# Artronix Jam

## Jeepers Bleepers 프로그램 1

아래는 0, 1, 2 번 핀에 연결된 LED 들의 불 빛을 깜박이는 프로그램 코드입니다.

```block
// Loop 3 blinking LEDs forever.
while(true) {
    // turn LEDS off
    pins.digitalWritePin(DigitalPin.P0, 0)
    basic.pause(500)
    pins.digitalWritePin(DigitalPin.P1, 0)
    basic.pause(500)
    pins.digitalWritePin(DigitalPin.P2, 0)
    basic.pause(500)

    // turn LEDs on.
    pins.digitalWritePin(DigitalPin.P0, 1)
    basic.pause(500)
    pins.digitalWritePin(DigitalPin.P1, 1)
    basic.pause(500)
    pins.digitalWritePin(DigitalPin.P2, 1)
    basic.pause(500)
}
```

# Jeepers Bleepers 프로그램 2

다음은 1 개의 LED 를 PWM(pulse width modulation) 방식으로, 서서히 켜고 끄는 프로그램 코드입니다.

```block
while (true) {
    for (let i = 0; i <= 128; i++) {
        pins.analogWritePin(AnalogPin.P0, i)
        basic.pause(10)
    }
    for (let i = 128; i >= 0; i--) {
        pins.analogWritePin(AnalogPin.P0, i)
        basic.pause(10)
    }
}
```