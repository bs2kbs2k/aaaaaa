# Advertise Url

블루투스 에디스톤(Eddystone) 프로토콜을 통해 URL 주소를 전송합니다.

## ~hint

## 블루투스 에디스톤(Eddystone)

블루투스 비콘 신호기들은, 특정 지역이나 어떤 물건 근처에 있다는 것을 알리기 위해 사용됩니다. 비콘 신호기들은 크기가 작은 데이터를 주변에 전송하기 위해서 블루투스 전송 기능을 사용하는데, 일정 거리 안에 있는 장치나 소프트웨어들이 그 데이터를 수신하고 동작하도록 할 수 있습니다. 일반적으로는 스마트폰과 앱이 비콘 신호기들에 반응하도록 할 수 있습니다.

비콘 신호는 여러 가지 포맷이 사용되는데, 비콘 신호 데이터를 포함하고 있는 블루투스 전송 패킷에 의해서 결정됩니다. iBeacon 은 Apple 의 비콘 신호 메시지 포맷입니다. 구글이 만든 비콘 신호 메시지 포맷은 블루투스 에디스톤(Eddystone) 입니다.

https://lancaster-university.github.io/microbit-docs/ble/eddystone/ 을 통해 더 살펴보세요.

## ~

```sig
bluetooth.advertiseUrl("https://makecode.microbit.org/", 7, true);
```

## 매개 변수

* `url`. 전송할 URL 주소가 포함되어있는 [문자열](/types/string). 프로토콜(예시: `https://`, 1 바이트로 처리됨)을 제외한 최대 17 문자
* `power`. [수(정수)](/types/number). 파워 레벨 0 (가까움) 부터 7 (멈).
* `connectable`. [불(boolean)](/blocks/logic/boolean) @boardname@ 가 연결을 수락할지 여부를 나타내는 값. 

## 예시: 비밀 코드 전송하기

```blocks
bluetooth.advertiseUrl("https://pxt.io?secret=42", 7, true);
```

## 참고 항목

[블루투스 전송 중단](/reference/bluetooth/stop-advertising), [블루투스 전송](/reference/bluetooth/advertise-uid)

```package
bluetooth
```