# 블루투스 UART 서비스

## ~hint

![](/static/bluetooth/Bluetooth_SIG.png)

@boardname@ 의 블루투스 "서비스"를 스마트폰과 같은 다른 장치에서 사용하고 싶은 경우에는, 그 이전에 [@boardname@ 와 페어링](/reference/bluetooth/bluetooth-pairing) 되어 있어야 합니다. 일단 먼저 페어링이 되고 나면, 그 장치를 @boardname@ 에 연결시킬 수 있고, @boardname@ 에서 지원되는 다양한 기능들과 관련한 데이터들을 주고 받을 수 있습니다.

## ~

블루투스 UART 서비스 를 사용하면, 스마트폰과 연결된 @boardname@ 사이에 작은 데이터들을 서로 교환할 수 있게 해줍니다. 작은 데이터들은 함께 결합되어 사용될 수 있습니다. [UART[(https://en.wikipedia.org/wiki/Universal_asynchronous_receiver/transmitter) Universal Asynchronous Receiver Transmitter 는 물리적 선으로 연결된 두 장치 사이에서 데이터를 주고 받는 시리얼 데이터 통신의 한 가지 방법입니다. 블루투스 UART 서비스는 실제 물리적 UART 시스템을 모방해서, 한 번에 한 방향으로 최대 20 바이트의 데이터를 전송할 수 있도록 해줍니다.

이 서비스가 사용될 때, @boardname@ 에는 60 바이트 크기의 버퍼를 만들어지고, 그 버퍼가 가득찰 때까지 데이터가 채워질 것입니다. @boardname@ 에서 UART 서비스를 사용할 때, 최대 3 조각으로 구성될 수 있는 전체 메시지가 연결된 장치로부터 전송되었다는 것을 나타내는 특별한 문자를 확인할 수 있습니다. 그 문자가 확인되면 @boardname@ 는 수신된 내용 전체를 버퍼에서 읽어와 해석하게 됩니다. 다시 말하자면, '구분 문자' 라고 불리는 이 특별한 문자는 @boardname@ 와 연결된 장치에서 "전체 메시지를 모두 전송했으니, 이제 사용해도 됩니다." 라는 의미로 사용됩니다.

UART 서비스는 다양한 목적으로 사용할 수 있습니다. 메시지 안에 어떤 내용을 넣던지 상관없고, 매우 좋은 융통성을 제공합니다. @boardname@ 와 스마트폰 사이에 질문과 답변이 왔다 갔다 하는 추측 게임도 만들 수 있고, 카메라에 @boardname@ 를 연결시켜 엣지 컨넥터를 통해 얻어진 이미지 데이터를, 블루투스를 통해 작은 데이터들로 만들어 스마트폰으로 전달시킬 수도 있습니다. 아주 많은 가능성들이 있습니다.

여러 가지 다른 장치들에서 블루투스 UART 서비스를 사용하기 위해서는, @boardname@ 에서 UART 버퍼를 통해 얻어진 데이터들을 읽을 수 있는 추가적인 코드가 필요하며, 다른 장치로 전달하기 위해 버퍼에 데이터를 쓰기 위해서도 추가적인 코드가 필요합니다.

```sig
bluetooth.startUartService();
```

## 예시: 블루투스 UART 서비스 시작하기

다음은 블루투스 UART 서비스를 시작시키는 코드입니다.:

```blocks
bluetooth.startUartService();
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