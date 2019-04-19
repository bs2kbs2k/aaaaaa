# 라디오 값 전송

Broadcast a [number](/reference/types/number) to other @boardname@s connected via `radio`.

```sig
radio.sendNumber(0);
```

### 매개 변수

* `value` - a [number](/reference/types/number) to send.

### 예시: 가속도 전송

다음은 @boardname@ 의 `가속도` 를 전송하는 예시입니다. `x축` (왼쪽 오른쪽 방향) 방향의 가속도를 다른 @boardname@ 들로 전송합니다. 이 프로그램은 장난감 자동차나 로켓의 가속도를 측정하는데 도움이 될 수 있습니다.

```blocks
input.onButtonPressed(Button.A, () => {
    radio.sendNumber(input.acceleration(Dimension.X))
})
```

### 빛 센서값 전송

다음 예제는 주변 빛의 양을 측정한 값을 전송합니다. [데이터 수신하면 실행](/reference/radio/on-data-packet-received) 예시와 함께 사용하면, 재미있는 것들을 할 수 있습니다.

```blocks
radio.setGroup(99)
basic.forever(() => {
    let level = input.lightLevel()
    radio.sendNumber(level)
})
```

### 참고 항목

[on data packet received](/reference/radio/on-data-packet-received)

```package
라디오
```