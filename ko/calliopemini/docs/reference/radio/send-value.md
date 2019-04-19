# 라디오 값 전송

[문자열]() 과 [수(정수)]() 를 함께 묶어, `라디오(radio)` 기능을 통해 @boardname@ 들에게 전송합니다. [문자열]() 의 최대 길이는 12 개 입니다.

```sig
radio.sendValue("name", 0);
```

### 매개 변수

* `name` is a [string](/reference/types/string) to send by radio
* `value` a [number](/reference/types/number) to send by radio

### 예시: 가속도 전송

다음 프로그램은 @boardname@ 의 **가속도** (속도가 빨라지거나 느려진 정도) 를 전송합니다. `x축` (왼쪽 오른쪽) 방향으로 측정된 가속도 값을 다른 @boardname@ 들에 전송합니다. 이 프로그램은 장난감 자동차나 로켓의 가속도를 측정하는데 도움이 될 수 있습니다.

```blocks
radio.setGroup(99)
input.onButtonPressed(Button.A, () => {
    radio.sendValue("acc", input.acceleration(Dimension.X))
})
```

다음은 수신된 문자열과 수를 수신하고, LED 스크린으로 출력합니다.

```blocks
radio.setGroup(99)
radio.onDataPacketReceived(({ receivedString, receivedNumber }) => {
    basic.showString(receivedString);
    basic.showNumber(receivedNumber);
});
```

### 참고 항목

[on data packet received](/reference/radio/on-data-packet-received)

```package
라디오
```