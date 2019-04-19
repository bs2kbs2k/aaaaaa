# 상태 유지(µs)

현재 수행하고 있는 작업 상태를, 마이크로초 단위로 대기(유지)시킵니다.

```sig
control.waitMicros(4)
```

### 예시

다음은 `P0` 핀을 통해 HIGH 펄스를 출력하는 동작을 10 마이크로초(µs) 동안 유지시키는 예시입니다.

```blocks
// ensure pin is low to send a clean pulse
pins.digitalWritePin(DigitalPin.P0, 0)
control.waitMicros(2)
// set pin to 1 and wait 10 micros
pins.digitalWritePin(DigitalPin.P0, 1)
control.waitMicros(10)
// finish pulse
pins.digitalWritePin(DigitalPin.P0, 0)
```

#### ~hint

이 함수는 시뮬레이터에서 지원되지 않습니다.

#### ~

### 참고 항목

[일시 중지](/reference/basic/pause)