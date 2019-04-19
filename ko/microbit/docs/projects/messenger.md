# 메신저

![](/static/mb/projects/a9-radio.png)

라디오 기능을 사용해 "YO" 메시지를 보내는 앱을 만들어보세요.

## 단계 1

`||input:on button pressed||` 블록을 이용해, 무선으로 `0` 을 전송합니다.

```blocks
input.onButtonPressed(Button.A, () => {
    radio.sendNumber(0);
});
```

## 단계 2

`||radio:on data packet received||` 블록을 사용해, 값 `0` 이 수신되면 "YO" 메시지를 출력하도록 만듭니다.

```blocks
let message = 0;
radio.onDataPacketReceived(({ receivedNumber }) => {
    message = receivedNumber;
    if (message == 0) {
        basic.showString("YO")
    }
})
```

프로그램을 @boardname@ 에 업로드하고, 다른 보드에도 업로드 합니다. 한 보드에서 **A** 버튼을 누르면, 다른 보드에서 메시지를 받을 수 있습니다.

## 단계 3

`||input:on button pressed||` 블록을 이용해, 무선으로 `1` 을 전송합니다.

```blocks
input.onButtonPressed(Button.B, () => {
    radio.sendNumber(1);
});
```

## 단계 4

`||radio:on data packet received||` 블록 안쪽에 블록들을 추가해, 값 `1` 이 수신되면 "BYE" 메시지를 출력하도록 만듭니다.

```blocks
let message = 0;
radio.onDataPacketReceived(({ receivedNumber }) => {
    message = receivedNumber;
    if (message == 0) {
        basic.showString("YO")
    }
    if (message == 1) {
        basic.showString("BYE")
    }
})
```

두 개의 @boardname@ 에 프로그램을 업로드 한 후, 메시지를 보내보세요!

```package
radio
```