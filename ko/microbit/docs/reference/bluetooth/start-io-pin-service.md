# 블루투스 입출력 핀 서비스 시작

## ~hint

![](/static/bluetooth/Bluetooth_SIG.png)

@boardname@ 의 블루투스 "서비스"를 스마트폰과 같은 다른 장치에서 사용하고 싶은 경우에는, 그 이전에 [@boardname@ 와 페어링](/reference/bluetooth/bluetooth-pairing) 되어 있어야 합니다. 일단 먼저 페어링이 되고 나면, 그 장치를 @boardname@ 에 연결시킬 수 있고, @boardname@ 에서 지원되는 다양한 기능들과 관련한 데이터들을 주고 받을 수 있습니다.

## ~

블루투스 입출력 핀 서비스는 무선으로 연결된 스마트폰과 같은 다른 장치에서, @boardname@ 의 엣지 컨넥터에 '연결된' 장치들과 통신할 수 있도록 해줍니다. 예를 들어 블루투스 입출력 핀 서비스를 사용하면, @boardname@ 에 연결되어있는 불 빛을 켜고 끌 수 있습니다. 또한, @boardname@ 에 연결되어있는 센서들로부터 수집되는 데이터들도 스마트폰으로 전송할 수 있게 됩니다. 사실, 두 가지 동작을 한 꺼번에 실행시킬 수도 있습니다. 블루투스 입출력 핀 서비스는, 엣지 컨넥터에 연결되어있는 여러 개의 각 '핀들'과 동시에 통신할 수 있도록 해주기 때문입니다.

다른 블루투스 장치의 입출력 핀 서비스를 사용하기 위해서, @boardname@ 에서는 별도의 추가적인 프로그램 코드가 필요하지 않습니다.

```sig
bluetooth.startIOPinService();
```

## 예시: 블루투스 입출력 핀 서비스 시작하기

다음은 블루투스 입출력 핀 서비스를 시작시키는 코드입니다.:

```blocks
bluetooth.startIOPinService();
```

## 동영상 - 블루투스 입출력 핀 서비스 - 3:49 부터 시작

http://www.youtube.com/watch?v=aep_GVowKfs

## 고급

스마트폰을 사용하는데 필요한 정보를 포함하고 있는, @boardname@ Bluetooth 입출력 핀 서비스와 관련한 고급 내용은 [Lancaster University @boardname@ runtime technical documentation](http://lancaster-university.github.io/microbit-docs/ble/iopin-service/) 를 살펴보세요.

## 참고 항목

[블루투스에 대하여](/reference/bluetooth/about-bluetooth), [@boardname@ 블루투스 프로파일 개요](http://lancaster-university.github.io/microbit-docs/ble/profile/), [@boardname@ 블루투스 프로파일 찾아보기](http://lancaster-university.github.io/microbit-docs/resources/bluetooth/microbit-profile-V1.9-Level-2.pdf), [@boardname@ 블루투스 자원](http://bluetooth-mdw.blogspot.co.uk/p/bbc-microbit.html), [블루투스 SIG](https://www.bluetooth.com)

```package
bluetooth
```