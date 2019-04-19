# 아날로그 입력

**아날로그** (`0` 부터 `1023`) 값으로 읽어옵니다. 설정한 [핀](/device/pins) 을 통해 입력되는 신호를 아날로그 값으로 읽어옵니다.

```sig
pins.analogReadPin(AnalogPin.P0)
```

## 매개 변수

* `name`. 핀 이름을 나타내는 [문자열](/types/string) (`P0` 부터 `P4`, `P10`)

## 리턴값

* [수(정수)](/types/number). `0` 부터 `1023`.

다음은 `P1` 핀을 아날로그 값으로 읽어 LED 스크린에 출력하는 예시 코드 입니다.

```blocks
basic.forever(() => {
    let value = pins.analogReadPin(AnalogPin.P1)
    basic.showNumber(value)
});
```

### ~hint

**아날로그 입력** 을 사용하는데, **아날로그 출력** 을 사용하는 다른 @boardname@ 가 있다면, 재미있는 것을 할 수 있습니다. @boardname@ 는 **아날로그 출력 설정** 으로 설정한 핀을 통해 디지털 값인 0 과 1 을 매우 빠르게 출력해서, 출력한 0 과 1 의 평균 값으로, 아날로그 출력 처럼 만들어 낼 수 있습니다. 하지만, 다른 @boardname@ 를 이용해 그 평균 값을 읽으려고하면, 그 @boardname@ 에서는 0 또는 1023 의 값으로 만 읽히게 됩니다. 그런 경우, 그 값들을 반복적으로 모두 더해 더 큰 수( 예를 들어, 100만)를 만든 후, 평균을 계산하는 방법을 사용할 수 있습니다. 다른 방법으로는, 두 @boardname@ 사이에 콘덴서(축전기)를 연결시키는 방법도 사용할 수 있습니다.

### ~

## 참고 항목

[@boardname@ 핀](/device/pins), [핀 연결(on)되면 실행](/reference/input/on-pin-pressed), [아날로그 출력](/reference/pins/analog-write-pin), [디지털 입력](/reference/pins/digital-read-pin), [디지털 출력](/reference/pins/digital-write-pin)