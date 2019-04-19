# 서보 펄스 설정

핀을 아날로그 출력(출력 주기 20 ms)처럼 만들고, 원하는 주기 값으로 변경합니다.

```sig
pins.servoSetPulse(AnalogPin.P1, 1500)
```

### 매개 변수

* `name`: a [string](/reference/types/string) that specifies the pin to configure (`P0` through `P4`, or `P10`)
* `micros`: a [number](/reference/types/number) that specifies the analog period in microseconds.

### 예시

다음은 서보 펄스 주기를 `1000` 마이크로초(µs)로 설정하는 예시 입니다. 1000 마이크로초(µs)는 1 밀리초(ms)

```blocks
pins.servoSetPulse(AnalogPin.P1, 1000)
```

### 참고 항목

[@boardname@ 핀](/device/pins), [핀 연결(on)되면 실행](/reference/input/on-pin-pressed), [아날로그 입력](/reference/pins/analog-read-pin), [디지털 입력](/reference/pins/digital-read-pin), [디지털 출력](/reference/pins/digital-write-pin)