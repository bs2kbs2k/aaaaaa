# 아날로그 출력

**아날로그** 신호 (`0` 부터 `1023`) 를 원하는 [핀](/device/pins) 으로 출력합니다.

```sig
pins.analogWritePin(AnalogPin.P0, 400)
```

## 매개 변수

* `name`. 핀 이름을 나타내는 [문자열](/types/string) (`P0` 부터 `P4`, `P10`)
* `value`. [수(정수)](/types/number). `0` 부터 `1023`.

## 예시

다음은 값 `1023` 을 `P0` 핀으로 출력하는 예시입니다.

```blocks
pins.analogWritePin(AnalogPin.P0, 1023)
```

### ~hint

(예를 들어) 값 `256` 출력시키면, *실제로* 값 `256` 정도로 출력하는 것이 아닙니다. 그 정도로 출력하는 것이 아니고, 출력되는 값들의 평균이 `256` 이 되는 것입니다.

### ~

## 참고 항목

[@boardname@ 핀](/device/pins), [핀 연결(on)되면 실행](/reference/input/on-pin-pressed), [아날로그 입력](/reference/pins/analog-read-pin), [디지털 입력](/reference/pins/digital-read-pin), [디지털 출력](/reference/pins/digital-write-pin)