# 블루투스 버튼 서비스 시작

### ~hint

![](/static/bluetooth/Bluetooth_SIG.png)

@boardname@ 의 블루투스 "서비스"를 스마트폰과 같은 다른 장치에서 사용하고 싶은 경우에는, 그 이전에 [@boardname@ 와 페어링](/reference/bluetooth/bluetooth-pairing) 되어 있어야 합니다. 일단 먼저 페어링이 되고 나면, 그 장치를 @boardname@ 에 연결시킬 수 있고, @boardname@ 에서 지원되는 다양한 기능들과 관련한 데이터들을 주고 받을 수 있습니다.

### ~

블루투스 버튼 서비스는 무선으로 연결된 스마트폰과 같은 다른 장치에서, @boardname@ 의 버튼 눌림 상태를 수신할 수 있도록 해줍니다. @boardname@ 에 있는 2 개의 각 버튼으로 가능한 3 가지 상태는 다음과 같습니다.:

* Not pressed(안 눌림)
* Pressed(눌림)
* Long press(길게 눌림) - 2 초 이상 길게 누른 상태 

블루투스 버튼 서비스를 사용하면, 연결된 @boardname@ 의 버튼에 반응하도록 할 수 있습니다. 예를 들어 @boardname@ 의 버튼들을 눌렀을 때, 방 어딘가에 숨겨져 있는 스마트폰에서 재미있는 소리가 나도록 할 수 있습니다. 그 외에 다른 재미있는 것들도 생각해보세요.

다른 블루투스 장치의 버튼 서비스를 사용하기 위해서, @boardname@ 에서는 별도의 추가적인 프로그램 코드가 필요하지 않습니다.

```sig
bluetooth.startButtonService();
```

### 예시: 블루투스 버튼 서비스 시작하기

다음은 블루투스 버튼 서비스를 시작시키는 코드입니다.:

```blocks
bluetooth.startButtonService();
```

### 동영상 - 블루투스 버튼 서비스 - 0:59 부터 시작

http://www.youtube.com/watch?v=aep_GVowKfs

### 고급

스마트폰을 사용하는데 필요한 정보를 포함하고 있는, @boardname@ Bluetooth 버튼 서비스와 관련한 고급 내용은 [Lancaster University @boardname@ runtime technical documentation](http://lancaster-university.github.io/microbit-docs/ble/button-service/) 를 살펴보세요.

### 참고 항목

[블루투스에 대하여](/reference/bluetooth/about-bluetooth), [@boardname@ 블루투스 프로파일 개요](http://lancaster-university.github.io/microbit-docs/ble/profile/), [@boardname@ 블루투스 프로파일 찾아보기](http://lancaster-university.github.io/microbit-docs/resources/bluetooth/microbit-profile-V1.9-Level-2.pdf), [@boardname@ 블루투스 자원](http://bluetooth-mdw.blogspot.co.uk/p/bbc-microbit.html), [블루투스 SIG](https://www.bluetooth.com)

```package
블루투스
```