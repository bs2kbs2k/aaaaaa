# 핀 끊어(off)지면 실행

[이벤트 핸들러](/reference/event-handler)(어떤 버튼이 눌린 것과 같은 이벤트가 발생했을 때, 실행되는 작은 프로그램)를 실행합니다. 이 핸들러는 핀 `0`, `1`, `2` 와 `GND` 가 연결되었다가 끊어지면 실행됩니다. 이 함수를 웹브라우저의 편집기에서 사용하는 경우, @boardname@ 의 핀을 직접 연결하는 대신에 시뮬레이터 화면에 있는 핀들을 클릭하면 됩니다.

`GND` 핀을 한 손으로 잡고, 다른 손으로 `0`, `1`, `2` 핀을 만지게 되면, 몸을 통해 아주 작은(안전한) 전류가 @boardname@ 로 흐르게 됩니다. 이렇게 전류가 흐르도록 하는 것을 **회로 완성하기** 라고 합니다. 몸이 큰 전기선과 같이 전기를 흘려주는 역할을 하는 것입니다!

```sig
input.onPinReleased(TouchPin.P0, () => {
})
```

## ~hint

이 함수는 @boardname@ 배터리와 연결되어있을 때, 더 잘 동작합니다. USB 케이블에 연결하지 않고 배터리를 사용해 전원을 공급하는 경우입니다.

## ~

## 매개 변수

* `핀 이름`. 끊김(off)을 감지할 핀 이름. `P0`, `P1`, `P2`

## 예시: 핀 연결 횟수 카운터

다음 코드는 `P0` 핀 끊김(off) 횟수를 카운트하는 예시입니다. 핀을 끊을 때마다 끊은 횟수를 카운트한 값을 LED 스크린에 출력합니다.

```blocks
let count = 0
basic.showNumber(count, 100)
input.onPinReleased(TouchPin.P0, () => {
    count = count + 1
    basic.showNumber(count, 100)
})
```

## 참고 항목

[@boardname@ 핀](/device/pins), [핀 연결(on)하면 실행](/reference/input/pin-is-pressed), [핀 아날로그 입력](/reference/pins/analog-read-pin), [핀 아날로그 출력](/reference/pins/analog-write-pin), [핀 디지털 입력](/reference/pins/digital-read-pin), [핀 디지털 출력](/reference/pins/digital-write-pin)