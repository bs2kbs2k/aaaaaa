# 블루투스 해제되면 실행

## ~hint

![](/static/bluetooth/Bluetooth_SIG.png)

@boardname@ 의 블루투스 "서비스"를 스마트폰과 같은 다른 장치에서 사용하고 싶은 경우에는, 그 이전에 [@boardname@ 와 페어링](/reference/bluetooth/bluetooth-pairing) 되어 있어야 합니다. 일단 먼저 페어링이 되고 나면, 그 장치를 @boardname@ 에 연결시킬 수 있고, @boardname@ 에서 지원되는 다양한 기능들과 관련한 데이터들을 주고 받을 수 있습니다.

## ~

이 블록은 [이벤트 처리기](/reference/event-handler) 를 실행시킵니다. @boardname@ 에 연결되었던 블루투스 장치가 끊기면 실행됩니다.

블루투스 장치가 끊기면 @boardname@ 의 LED 스크린에 "D" 문자를 출력하도록 할 수 있습니다.

```sig
bluetooth.onBluetoothDisconnected(() => {
});
```

## 예시: @boardname@ 와의 연결이 끊기면 "D" 출력하기

```blocks
bluetooth.onBluetoothDisconnected(() => {
    basic.showString("D");
});
```

## 동영상 - 블루투스 해제되면 실행

http://www.youtube.com/watch?v=HyBcsD9Eh6I

## 참고 항목

[블루투스에 대하여](/reference/bluetooth/about-bluetooth), [@boardname@ 블루투스 프로파일 개요](http://lancaster-university.github.io/microbit-docs/ble/profile/), [@boardname@ 블루투스 프로파일 찾아보기](http://lancaster-university.github.io/microbit-docs/resources/bluetooth/microbit-profile-V1.9-Level-2.pdf), [@boardname@ 블루투스 자원](http://bluetooth-mdw.blogspot.co.uk/p/bbc-microbit.html), [블루투스 SIG](https://www.bluetooth.com)

```package
bluetooth
```