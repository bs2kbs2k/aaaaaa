# 펄스 입력(µs)

@boardname@ 의 [핀](/device/pins) 으로 입력되는, 펄스 (high 또는 low) 의 주기를 알아냅니다.

```sig
pins.pulseIn(DigitalPin.P0, PulseValue.High)
```

### ~avatar

일부 핀들은 [LED 스크린](/device/screen) 을 위해 사용됩니다. 자세한 사항은 [핀 설명](/device/pins) 에서 살펴볼 수 있습니다.

### ~

### 매개 변수

* `name` is a [string](/reference/types/string) that stores the name of the pin (`P0`, `P1`, or `P2`, up through `P20`)
* `value`. 측정할 펄스 값, `high` 또는 `low`
* `maxDuration`. 펄스 입력이 없을 경우 마이크로초 단위 최대 주기 

### 리턴값

* a [number](/reference/types/number) that represents the pulse duration in micro-seconds

### 예시: 초음파 센서로 거리 측정하기

다음은 `P0` 를 통해 HC-SR04 초음파 센서에 펄스를 출력하고, 측정된 거리를 읽어오는 예시입니다.

```blocks
basic.forever(() => {
    // send pulse
    pins.digitalWritePin(DigitalPin.P0, 0)
    control.waitMicros(2)
    pins.digitalWritePin(DigitalPin.P0, 1)
    control.waitMicros(10)
    pins.digitalWritePin(DigitalPin.P0, 0)

    // read pulse
    led.plotBarGraph(pins.pulseIn(DigitalPin.P1, PulseValue.High) / 58, 0)
    basic.pause(100)
})
```

#### ~hint

이 함수는 시뮬레이터에서 지원되지 않습니다.

#### ~

### 참고 항목

[디지털 출력](/reference/pins/digital-write-pin),