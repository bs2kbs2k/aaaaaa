# 라디오 값 전송

[수(정수)](/types/number) 값을 다른 @boardname@ 들에 전송합니다. `라디오(radio)` 기능을 사용합니다.

```sig
radio.sendNumber(0);
```

## 매개 변수

* `값` - 전송할 [수(정수)](/types/number) 값.

## 예시: 가속도 전송

다음은 @boardname@ 의 `가속도` 를 전송하는 예시입니다. `x축` (왼쪽 오른쪽 방향) 방향의 가속도를 다른 @boardname@ 들로 전송합니다. 이 프로그램은 장난감 자동차나 로켓의 가속도를 측정하는데 도움이 될 수 있습니다.

```blocks
input.onButtonPressed(Button.A, () => {
    radio.sendNumber(input.acceleration(Dimension.X))
})
```

## 빛 센서값 전송

다음 예제는 주변 빛의 양을 측정한 값을 전송합니다. [데이터 수신하면 실행](/reference/radio/on-data-packet-received) 예시와 함께 사용하면, 재미있는 것들을 할 수 있습니다.

```blocks
radio.setGroup(99)
basic.forever(() => {
    let level = input.lightLevel()
    radio.sendNumber(level)
})
```

## 참고 항목

[라디오 데이터 수신하면 실행](/reference/radio/on-data-packet-received)

```package
radio
```