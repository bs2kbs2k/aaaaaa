# 아날로그 PWM 설정 주기

아날로그 [핀](/device/pins) 의 PWM(Pulse Width Modulation) 주기를 설정합니다. 이 함수를 사용하려면 먼저, 해당 핀을 아날로그 출력 모드로 바꿔주어야 합니다.

```sig
pins.analogSetPeriod(AnalogPin.P0, 20000)
```

## 매개 변수

* `name`. 설정할 핀 이름을 나타내는 [문자열](/types/string) (`P0` 부터 `P4`, `P10`)
* `micros`. [수(정수)](/types/number). 설정할 신호 출력 주기. 마이크로초(µs) 단위

다음은 `P0` 핀을 **아날로그 출력** 으로 설정한 후, `P0` 핀의 PWM 주기를 20,000 마이크로초로 변경하는 예시입니다. 20,000 마이크로초는 20 밀리초이며, 0.02 초를 의미합니다.

```blocks
pins.analogWritePin(AnalogPin.P0, 512)
pins.analogSetPeriod(AnalogPin.P0, 20000)
```

## 참고 항목

[@boardname@ 핀](/device/pins), [핀 연결(on)되면 실행](/reference/input/on-pin-pressed), [아날로그 입력](/reference/pins/analog-read-pin), [아날로그 출력](/reference/pins/analog-write-pin), [디지털 입력](/reference/pins/digital-read-pin), [디지털 출력](/reference/pins/digital-write-pin)