# 아날로그 출력

**아날로그** 신호 (`0` 부터 `1023`) 를 원하는 [핀](/device/pins) 으로 출력합니다.

```sig
pins.analogWritePin(AnalogPin.P1, 400)
```

### 매개 변수

* `name` is a [string](/reference/types/string) that is the pin name you say (`P0` through `P4`, or `P10`)
* `value` is a [number](/reference/types/number) from `0` through `1023`

### 예시

다음은 값 `1023` 을 `P0` 핀으로 출력하는 예시입니다.

```blocks
pins.analogWritePin(AnalogPin.P1, 1023)
```

#### ~hint

(예를 들어) 값 `256` 출력시키면, *실제로* 값 `256` 정도로 출력하는 것이 아닙니다. 그 정도로 출력하는 것이 아니고, 출력되는 값들의 평균이 `256` 이 되는 것입니다.

#### ~

### 참고 항목

[@boardname@ 핀](/device/pins), [핀 연결(on)되면 실행](/reference/input/on-pin-pressed), [아날로그 입력](/reference/pins/analog-read-pin), [디지털 입력](/reference/pins/digital-read-pin), [디지털 출력](/reference/pins/digital-write-pin)