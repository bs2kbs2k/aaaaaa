# 핀 연결(on) 상태

핀이 연결(on)되었는지 아닌지를 확인할 수 있습니다.

`GND` 핀을 한 손으로 잡고, 다른 손으로 `0`, `1`, `2` 핀을 만지게 되면, 몸을 통해 아주 작은(안전한) 전류가 @boardname@ 로 흐르게 됩니다. 이렇게 전류가 흐르도록 하는 것을 **회로 완성하기** 라고 합니다. 몸이 큰 전기선과 같이 전기를 흘려주는 역할을 하는 것입니다!

```sig
input.pinIsPressed(TouchPin.P0);
```

## ~hint

이 함수는 @boardname@ 배터리와 연결되어있을 때, 더 잘 동작합니다. USB 케이블에 연결하지 않고 배터리를 사용해 전원을 공급하는 경우입니다.

## ~

### 매개 변수

* a [string](/reference/types/string) that holds the pin name (**P0**, **P1**, or **P2**)

### 리턴값

* [불(true/false)](/blocks/logic/boolean). 핀이 연결(on)되었는지를 나타내는 불 값(`true`, `false`)

### 예시

다음은 `1`(`P0` 가 연결된경우), `0`(`P0` 가 연결되지 않은 경우)을 출력하는 예시 코드입니다.:

```blocks
basic.forever(() => {
    if (input.pinIsPressed(TouchPin.P0)) {
        basic.showNumber(1, 150)
    } else {
        basic.showNumber(0, 150)
    }
})
```

### 참고 항목

[@boardname@ 핀](/device/pins), [핀 연결(on) 상태](/reference/input/on-pin-pressed), [핀 아날로그 입력](/reference/pins/analog-read-pin), [핀 아날로그 출력](/reference/pins/analog-write-pin), [핀 디지털 입력](/reference/pins/digital-read-pin), [핀 디지털 출력](/reference/pins/digital-write-pin)