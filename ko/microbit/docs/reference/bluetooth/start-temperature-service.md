# 블루투스 온도 센서 서비스

## ~hint

![](/static/bluetooth/Bluetooth_SIG.png)

@boardname@ 의 블루투스 "서비스"를 스마트폰과 같은 다른 장치에서 사용하고 싶은 경우에는, 그 이전에 [@boardname@ 와 페어링](/reference/bluetooth/bluetooth-pairing) 되어 있어야 합니다. 일단 먼저 페어링이 되고 나면, 그 장치를 @boardname@ 에 연결시킬 수 있고, @boardname@ 에서 지원되는 다양한 기능들과 관련한 데이터들을 주고 받을 수 있습니다.

## ~

@boardname@ 는 주변의 현재 온도를 대략적으로 측정하고 그 온도 값을 전송할 수 있습니다. 그 온도는 CPU 의 온도를 이용해 간접적으로 측정한 것이기 때문에, 그 주변의 대략적인 온도 값이라고 할 수 있습니다. 블루투스 온도 센서 서비스는, 무선으로 연결된 스마트폰에 @boardname@ 에서 측정되는 실시간 온도 변화 값을 읽어올 수 있습니다. 온도 값은 섭씨 단위로 표현됩니다.

블루투스 온도 센서 서비스를 사용하면, @boardname@ 실시간으로 측정하는 주변 온도 값을 이용해, 스마트폰이나 태블릿을 디지털/그래픽 온도계처럼 만들 수 있습니다.

다른 블루투스 장치의 온도 센서 서비스를 사용하기 위해서, @boardname@ 에서는 별도의 추가적인 프로그램 코드가 필요하지 않습니다.

```sig
bluetooth.startTemperatureService();
```

## 예시: 블루투스 온도 센서 서비스 시작하기

다음은 블루투스 온도 센서 서비스를 시작시키는 코드입니다.:

```blocks
bluetooth.startTemperatureService();
```

## 동영상 - 블루투스 온도 센서 서비스 - 3:05 부터 시작

http://www.youtube.com/watch?v=aep_GVowKfs

## 고급

스마트폰을 사용하는데 필요한 정보를 포함하고 있는, @boardname@ Bluetooth 온도 센서 서비스와 관련한 고급 내용은 [Lancaster University @boardname@ runtime technical documentation](http://lancaster-university.github.io/microbit-docs/ble/temperature-service/) 를 살펴보세요.

## 참고 항목

[블루투스에 대하여](/reference/bluetooth/about-bluetooth), [@boardname@ 블루투스 프로파일 개요](http://lancaster-university.github.io/microbit-docs/ble/profile/), [@boardname@ 블루투스 프로파일 찾아보기](http://lancaster-university.github.io/microbit-docs/resources/bluetooth/microbit-profile-V1.9-Level-2.pdf), [@boardname@ 블루투스 자원](http://bluetooth-mdw.blogspot.co.uk/p/bbc-microbit.html), [블루투스 SIG](https://www.bluetooth.com)

```package
bluetooth
```