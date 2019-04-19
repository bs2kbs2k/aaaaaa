# 블루투스 LED 서비스 시작

### ~hint

![](/static/bluetooth/Bluetooth_SIG.png)

@boardname@ 의 블루투스 "서비스"를 스마트폰과 같은 다른 장치에서 사용하고 싶은 경우에는, 그 이전에 [@boardname@ 와 페어링](/reference/bluetooth/bluetooth-pairing) 되어 있어야 합니다. 일단 먼저 페어링이 되고 나면, 그 장치를 @boardname@ 에 연결시킬 수 있고, @boardname@ 에서 지원되는 다양한 기능들과 관련한 데이터들을 주고 받을 수 있습니다.

### ~

블루투스 LED 서비스는 무선으로 연결된 스마트폰과 같은 다른 장치에서, @boardname@ 의 LED 매트릭스 스크린에 출력할 짧은 문자열이나 패턴들을 전송 할 수 있도록 해줍니다. @boardname@ 에서 수신된 문자열은 LED 스크린에서 스크롤되며, 스크롤 시간도 블루투스 LED 서비스를 통해 조절할 수 있습니다. 또한 LED 서비스를 사용하는 장치는, @boardname@ 의 현재 LED 매트릭스의 불 빛 상태들 읽어올 수 있습니다.

따라서, 예를 들어 스마트폰에서 웃는 모양을 그린 후 버튼을 눌렀을 때, 방의 다른 쪽에 있는 @boardname@ 에서 그 모양이 출력되도록 할 수 있습니다. 또는, 스마트폰에서 메시지/이메일/소셜미디어메시지 수신을 알리면, @boardname@ 에 메시지를 출력하는 프로그램도 만들 수 있습니다. @boardname@ 를 마치 스마트워치처럼 사용하면서, 스마트폰은 가방 안에 넣어 둘 수 있는 것입니다.

다른 블루투스 장치의 LED 서비스를 사용하기 위해서, @boardname@ 에서는 별도의 추가적인 프로그램 코드가 필요하지 않습니다.

```sig
bluetooth.startLEDService();
```

### 예시: 블루투스 LED 서비스 시작하기

다음은 블루투스 LED 서비스를 시작시키는 코드입니다.:

```blocks
bluetooth.startLEDService();
```

### 동영상 - 블루투스 LED 서비스 - 2:00 부터 시작

http://www.youtube.com/watch?v=aep_GVowKfs

### 고급

스마트폰을 사용하는데 필요한 정보를 포함하고 있는, @boardname@ Bluetooth LED 서비스와 관련한 고급 내용은 [Lancaster University @boardname@ runtime technical documentation](http://lancaster-university.github.io/microbit-docs/ble/led-service/) 를 살펴보세요.

### 참고 항목

[블루투스에 대하여](/reference/bluetooth/about-bluetooth), [@boardname@ 블루투스 프로파일 개요](http://lancaster-university.github.io/microbit-docs/ble/profile/), [@boardname@ 블루투스 프로파일 찾아보기](http://lancaster-university.github.io/microbit-docs/resources/bluetooth/microbit-profile-V1.9-Level-2.pdf), [@boardname@ 블루투스 자원](http://bluetooth-mdw.blogspot.co.uk/p/bbc-microbit.html), [블루투스 SIG](https://www.bluetooth.com)

```package
블루투스
```