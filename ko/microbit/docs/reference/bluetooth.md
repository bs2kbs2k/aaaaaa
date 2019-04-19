# 블루투스

추가 블루투스 서비스에 대한 지원

## ~hint

![](/static/bluetooth/Bluetooth_SIG.png)

@boardname@ 의 블루투스 "서비스"를 스마트폰과 같은 다른 장치에서 사용하고 싶은 경우에는, 그 이전에 [@boardname@ 와 페어링](/reference/bluetooth/bluetooth-pairing) 되어 있어야 합니다. 일단 먼저 페어링이 되고 나면, 그 장치를 @boardname@ 에 연결시킬 수 있고, @boardname@ 에서 지원되는 다양한 기능들과 관련한 데이터들을 주고 받을 수 있습니다.

## ~

```cards
bluetooth.startAccelerometerService();
bluetooth.startButtonService();
bluetooth.startIOPinService();
bluetooth.startLEDService();
bluetooth.startMagnetometerService();
bluetooth.startTemperatureService();
bluetooth.onBluetoothConnected(() => {});
bluetooth.onBluetoothDisconnected(() => {});
bluetooth.setTransmitPower(7);
```

## 블루투스 UART

```cards
bluetooth.startUartService();
bluetooth.uartReadUntil("");
bluetooth.uartWriteString("");
bluetooth.uartWriteNumber(0);
bluetooth.uartWriteValue("", 0);
bluetooth.onUartDataReceived(",", () => {})
```

## 블루투스 에디스톤(Eddystone)

```cards
bluetooth.advertiseUid(42, 1, 7, true);
bluetooth.advertiseUrl("https://makecode.microbit.org/", 7, true);
bluetooth.stopAdvertising();
```

## 고급

스마트폰을 사용하는데 필요한 정보를 포함하고 있는, @boardname@ Bluetooth UART 서비스와 관련한 고급 내용은 [Lancaster University @boardname@ runtime technical documentation](http://lancaster-university.github.io/microbit-docs/ble/uart-service/) 를 살펴보세요.

## 참고 항목

[블루투스 가속도 센서 서비스 시작](/reference/bluetooth/start-accelerometer-service), [블루투스 버튼 서비스 시작](/reference/bluetooth/start-button-service), [블루투스 입출력 핀 서비스 시작](/reference/bluetooth/start-io-pin-service), [블루투스 LED 서비스 시작](/reference/bluetooth/start-led-service), [블루투스 자기 센서 서비스 시작](/reference/bluetooth/start-magnetometer-service), [블루투스 온도 센서 서비스 시작](/reference/bluetooth/start-temperature-service), [블루투스 UART 서비스 시작](/reference/bluetooth/start-uart-service), [블루투스 UART 문자까지 읽기](/reference/bluetooth/uart-read-until), [블루투스 UART 문자열 전송](/reference/bluetooth/uart-write-string), [블루투스 UART 정수 전송](/reference/bluetooth/uart-write-number), [블루투스 UART 변수 값 전송](/reference/bluetooth/uart-write-value), [블루투스 연결되면 실행](/reference/bluetooth/on-bluetooth-connected), [블루투스 해제되면 실행](/reference/bluetooth/on-bluetooth-disconnected), [블루투스 URL 전송](/reference/bluetooth/advertise-url), [블루투스 전송 중단](/reference/bluetooth/stop-advertising)

```package
bluetooth
```