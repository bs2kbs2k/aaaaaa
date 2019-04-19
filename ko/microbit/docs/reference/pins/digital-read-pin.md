# 디지털 입력

**디지털** (`0` 또는 `1`) 신호를 읽어옵니다. @boardname@ 의 [핀](/device/pins) 을 통해 입력되는 신호를 읽어옵니다.

```sig
pins.digitalReadPin(DigitalPin.P3)
```

## ~avatar

일부 핀들은 [LED 스크린](/device/screen) 을 위해 사용됩니다. 자세한 사항은 [핀 설명](/device/pins) 에서 살펴볼 수 있습니다.

## ~

## 매개 변수

* `name`. 핀 이름을 나타내는 [문자열](/types/string) (`P0`, `P1`, `P2`, ... , `P20`)

## 리턴값

* [수(정수)](/types/number). `0` 또는 `1`.

## 예시: 축구 점수판

다음은 `P0` 의 신호를 읽어, 점수를 올리는 예시 코드입니다. `P0` 포트의 디지털 입력 값이 `1` 이면, 점수를 올리고 `P2` 를 통해 부저음을 출력합니다. 부저음은 `디지털 출력` 을 이용해 출력할 수 있습니다.

```blocks
let score = 0
basic.showNumber(score)
basic.forever(() => {
    if (pins.digitalReadPin(DigitalPin.P0) == 1) {
        score++;
        pins.digitalWritePin(DigitalPin.P2, 1)
        basic.showNumber(score)
        basic.pause(1000)
        pins.digitalWritePin(DigitalPin.P2, 0)
    }
})
```

다음은 점수판 프로그램에 연동해서 사용할 수 있는 리모트 프로그램입니다. 리모트 @boardname@ 의 `P1` 포트와 점수판 @boardname@ 의 `P0` 포트를 연결시키고 리모트 장치의 `B` 버튼을 누르면, 부저음이 울리고 점수판 @boardname@ 의 점수를 올려줍니다.

```blocks
input.onButtonPressed(Button.B, () => {
    pins.digitalWritePin(DigitalPin.P1, 1);
    basic.pause(500);
    pins.digitalWritePin(DigitalPin.P1, 0);
});
```

### ~hint

두 @boardname@ 의 `GND` 핀을 서로 연결해야합니다!

### ~

## 참고 항목

[@boardname@ 핀](/device/pins), [디지털 출력](/reference/pins/digital-write-pin), [아날로그 입력](/reference/pins/analog-read-pin), [아날로그 출력](/reference/pins/analog-write-pin), [핀 연결(on)되면 실행](/reference/input/on-pin-pressed), [핀 연결(on) 상태](/reference/input/pin-is-pressed)