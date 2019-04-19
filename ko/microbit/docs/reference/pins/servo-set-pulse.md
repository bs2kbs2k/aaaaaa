# 서보 펄스 설정

핀을 아날로그 출력(출력 주기 20 ms)처럼 만들고, 원하는 주기 값으로 변경합니다.

```sig
pins.servoSetPulse(AnalogPin.P1, 1500)
```

## 매개 변수

* `name`. 설정할 핀 이름을 나타내는 [문자열](/types/string) (`P0` 부터 `P4`, `P10`)
* `micros`. [수(정수)](/types/number). 설정할 신호 출력 주기. 마이크로초(µs) 단위

## 예시

다음은 서보 펄스 주기를 `1000` 마이크로초(µs)로 설정하는 예시 입니다. 1000 마이크로초(µs)는 1 밀리초(ms)

```blocks
pins.servoSetPulse(AnalogPin.P0, 1000)
```

## 참고 항목

[@boardname@ 핀](/device/pins), [핀 연결(on)되면 실행](/reference/input/on-pin-pressed), [아날로그 입력](/reference/pins/analog-read-pin), [디지털 입력](/reference/pins/digital-read-pin), [디지털 출력](/reference/pins/digital-write-pin)