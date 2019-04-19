# Advertise UID

블루투스 에디스톤(Eddystone) 프로토콜을 통해 UID를 전송합니다.

## ~hint

## 블루투스 에디스톤(Eddystone)

블루투스 비콘 신호기들은, 특정 지역이나 어떤 물건 근처에 있다는 것을 알리기 위해 사용됩니다. 비콘 신호기들은 크기가 작은 데이터를 주변에 전송하기 위해서 블루투스 전송 기능을 사용하는데, 일정 거리 안에 있는 장치나 소프트웨어들이 그 데이터를 수신하고 동작하도록 할 수 있습니다. 일반적으로는 스마트폰과 앱이 비콘 신호기들에 반응하도록 할 수 있습니다.

비콘 신호는 여러 가지 포맷이 사용되는데, 비콘 신호 데이터를 포함하고 있는 블루투스 전송 패킷에 의해서 결정됩니다. iBeacon 은 Apple 의 비콘 신호 메시지 포맷입니다. 구글이 만든 비콘 신호 메시지 포맷은 블루투스 에디스톤(Eddystone) 입니다.

https://lancaster-university.github.io/microbit-docs/ble/eddystone/ 을 통해 더 살펴보세요.

## ~

```sig
bluetooth.advertiseUid(42, 1, 7, true);
```

## 매개 변수

* `namespace`. namespace uid (6 to 9) 의 마지막 4 바이트
* `instance` instance (2 to 5) 의 마지막 4 바이트
* `power`. [수(정수)](/types/number). 파워 레벨 0 (가까움) 부터 7 (멈).
* `connectable`. [불(boolean)](/blocks/logic/boolean) @boardname@ 가 연결을 수락할지 여부를 나타내는 값. 

## 인코딩

`namespace` 와 `instance` 의 바이트들은 10 바이트 UID namespace 와 6 바이트 UID instance 를 만들어낼 수 있도록 인코딩됩니다.

    UID namespace: [0, ..., namespace]
    UID instance: [0, ..., instance]
    

## 참고 항목

[블루투스 전송 중단](/reference/bluetooth/stop-advertising), [블루투스 UID 버퍼](/reference/bluetooth/advertise-uid-buffer)

```package
bluetooth
```