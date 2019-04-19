# 라디오 문자열 전송

라디오 기능으로 연결되어있는 다른 @boardname@ 들에게 문자열을 전송합니다. 문자열의 최대 길이는 19 문자 입니다.

```sig
radio.sendString("Hello!")
```

### 매개 변수

* `msg` is a [string](/reference/types/string) to send by radio.

### 예시: 양방향 라디오

이 프로그램을 2 개 이상의 @boardname@ 에 업로드하면, `A` 버튼을 눌러 다른 보드에 문자열을 전송할 수 있습니다. 다른 @boardname@ 들은 수신한 문자열을 출력할 것입니다.

```blocks
input.onButtonPressed(Button.A, () => {
    radio.sendString("Codeword: TRIMARAN")
    basic.showString("SENT");
})

radio.onDataPacketReceived(({ receivedString }) => {
    basic.showString(receivedString);
});
```

### ~hint

라디오 데이터를 전송하면서 동시에 수신할 수 있는 장치를 *트랜시버(transceiver)* 라고도 부릅니다.

### ~

### 참고 항목

[on data packet received](/reference/radio/on-data-packet-received)

```package
라디오
```