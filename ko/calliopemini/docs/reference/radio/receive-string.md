# 라디오 문자열 수신

> 참고: 이 API는 더 이상 사용되지 않습니다! 대신 [라디오 데이터 수신하면 실행](/reference/radio/on-data-packet-received) 을 사용하세요.

`라디오(radio)` 기능을 통해 @boardname@ 에서 전송된 문자열을 읽어옵니다.

```sig
radio.receiveString()
```

### 리턴값

* the first [string](/reference/types/string) that was sent. If no string was sent, then this function returns an empty (blank) string.

### 예시: 간단한 수신기

다른 @boardname@ 가 전송한 문자열을 출력합니다.

```blocks
radio.onDataReceived(() => {
    basic.showString(radio.receiveString());
});
```

### 예시: 양방향 라디오

이 프로그램을 2 개 이상의 @boardname@ 에 업로드하면, `A` 버튼을 눌러 다른 보드에 문자열을 전송할 수 있습니다. 다른 @boardname@ 들은 수신한 문자열 코드를 출력할 것입니다.

```blocks
input.onButtonPressed(Button.A, () => {
    radio.sendString("Codeword: TRIMARAN")
    basic.showString("SENT");
})

radio.onDataReceived(() => {
    basic.showString(radio.receiveString());
});
```

### ~hint

라디오 데이터를 전송하면서 동시에 수신할 수 있는 장치를 *트랜시버(transceiver)* 라고도 부릅니다.

### ~

### 예시: 감정 전송

다음은 행복함 또는 슬픔을 전송하는 간단한 예시 코드입니다. ```라디오```. `A` 또는 `B 버튼을 이용해` 감정을 선택할 수 있습니다.

이 프로그램은 다른 친구들의 감정도 수신합니다.

```blocks
let data: string = "";
input.onButtonPressed(Button.A, () => {
    radio.sendString("H");
});
input.onButtonPressed(Button.B, () => {
    radio.sendString("S");
});
radio.onDataReceived(() => {
    data = radio.receiveString();
    if ("H" == data) {
        basic.showLeds(`
            . . . . .
            . # . # .
            . . . . .
            # . . . #
            . # # # .
            `);
    } else if ("S" == data) {
        basic.showLeds(`
            . . . . .
            . # . # .
            . . . . .
            . # # # .
            # . . . #
            `);
    } else {
        basic.showString("?");
    }
});
```

### 참고 항목

[라디오 문자열 전송](/reference/radio/send-string), [라디오 데이터 수신하면 실행](/reference/radio/on-data-received)

```package
라디오
```