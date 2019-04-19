# 블루투스

추가 블루투스 서비스에 대한 지원

### ~hint

![](/static/bluetooth/Bluetooth_SIG.png)

@boardname@ 의 블루투스 "서비스"를 스마트폰과 같은 다른 장치에서 사용하고 싶은 경우에는, 그 이전에 [@boardname@ 와 페어링](/reference/bluetooth/bluetooth-pairing) 되어 있어야 합니다. 일단 먼저 페어링이 되고 나면, 그 장치를 @boardname@ 에 연결시킬 수 있고, @boardname@ 에서 지원되는 다양한 기능들과 관련한 데이터들을 주고 받을 수 있습니다.

### ~

```cards
bluetooth.startAccelerometerService();
bluetooth.startButtonService();
bluetooth.startIOPinService();
bluetooth.startLEDService();
bluetooth.startMagnetometerService();
bluetooth.startTemperatureService();
bluetooth.onBluetoothConnected(() => {});
bluetooth.onBluetoothDisconnected(() => {});
```

## 블루투스 UART

```cards
bluetooth.startUartService();
bluetooth.uartReadUntil("");
bluetooth.uartWriteString("");
bluetooth.uartWriteNumber(0);
bluetooth.uartWriteValue("", 0);
```

```package
블루투스
```

### 고급

스마트폰을 사용하는데 필요한 정보를 포함하고 있는, @boardname@ Bluetooth UART 서비스와 관련한 고급 내용은 [Lancaster University @boardname@ runtime technical documentation](http://lancaster-university.github.io/microbit-docs/ble/uart-service/) 를 살펴보세요.

### 참고 항목

[startAccelerometerService](/reference/bluetooth/start-accelerometer-service), [startButtonService](/reference/bluetooth/start-button-service), [startIOPinService](/reference/bluetooth/start-io-pin-service), [startLEDService](/reference/bluetooth/start-led-service), [startMagnetometerService](/reference/bluetooth/start-magnetometer-service), [startTemperatureService](/reference/bluetooth/start-temperature-service), [startUartService](/reference/bluetooth/start-uart-service), [uartReadUntil](/reference/bluetooth/uart-read-until), [uartWriteString](/reference/bluetooth/uart-write-string), [uartWriteNumber](/reference/bluetooth/uart-write-number), [uartWriteValue](/reference/bluetooth/uart-write-value), [onBluetoothConnected](/reference/bluetooth/on-bluetooth-connected), [onBluetoothDisconnected](/reference/bluetooth/on-bluetooth-disconnected)