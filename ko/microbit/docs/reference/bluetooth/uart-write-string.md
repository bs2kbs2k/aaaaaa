# 블루투스 UART 문자열 전송

## ~hint

![](/static/bluetooth/Bluetooth_SIG.png)

@boardname@ 의 블루투스 "서비스"를 스마트폰과 같은 다른 장치에서 사용하고 싶은 경우에는, 그 이전에 [@boardname@ 와 페어링](/reference/bluetooth/bluetooth-pairing) 되어 있어야 합니다. 일단 먼저 페어링이 되고 나면, 그 장치를 @boardname@ 에 연결시킬 수 있고, @boardname@ 에서 지원되는 다양한 기능들과 관련한 데이터들을 주고 받을 수 있습니다.

## ~

[블루투스 UART 서비스](/reference/bluetooth/start-uart-service) 를 사용하면, 스마트폰과 연결된 @boardname@ 사이에 작은 데이터들을 서로 교환할 수 있게 해줍니다.

블루투스 UART 서비스가 실행 중이면, @boardname@ 가 블루투스로 연결된 장치에 데이터를 전송할 수 있도록 해줍니다.

```sig
bluetooth.uartWriteString("");
```

## 예시: 블루투스 UART 서비스를 시작하고, A 버튼을 누를 때마다 블루투스로 연결된 다른 장치에 "HELLO" 메시지를 전송합니다.

```blocks
let connected = 0;
bluetooth.onBluetoothConnected(() => {
    basic.showString("C");
    connected = 1;
});
bluetooth.onBluetoothDisconnected(() => {
    basic.showString("D");
    connected = 0;
});
input.onButtonPressed(Button.A, () => {
    if (connected == 1) {
        bluetooth.uartWriteString("HELLO");
    }
});
```

## 동영상 - UART 서비스 추측 게임

https://www.youtube.com/watch?v=PgGeWddMAZ0

## 고급

스마트폰을 사용하는데 필요한 정보를 포함하고 있는, @boardname@ Bluetooth UART 서비스와 관련한 고급 내용은 [Lancaster University @boardname@ runtime technical documentation](http://lancaster-university.github.io/microbit-docs/ble/uart-service/) 를 살펴보세요.

## 참고 항목

[블루투스에 대하여](/reference/bluetooth/about-bluetooth), [@boardname@ 블루투스 프로파일 개요](http://lancaster-university.github.io/microbit-docs/ble/profile/), [@boardname@ 블루투스 프로파일 찾아보기](http://lancaster-university.github.io/microbit-docs/resources/bluetooth/microbit-profile-V1.9-Level-2.pdf), [@boardname@ 블루투스 자원](http://bluetooth-mdw.blogspot.co.uk/p/bbc-microbit.html), [블루투스 SIG](https://www.bluetooth.com)

```package
bluetooth
```