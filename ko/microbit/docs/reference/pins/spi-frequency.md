# SPI통신 주파수

SPI통신 주파수를 설정합니다.

```sig
pins.spiFrequency(1000000);
```

## 매개 변수

* **주파수**: SPI 버스 클록 주파수로 설정하려는 [수(정수)](/types/number). 초당 클록 수(Hz).

## 예시

SPI통신 버스로 연결된 장치에서 *WHOAMI* 레지스터의 값을 읽어옵니다. 칩 선택 라인은 **0** 번 핀에 연결되어있고, SPI통신 신호는 **13**, **14**, **15** 번 핀을 사용합니다.

```blocks
pins.digitalWritePin(DigitalPin.P0, 1);
pins.spiPins(DigitalPin.P15, DigitalPin.P14, DigitalPin.P13);
pins.spiFormat(8, 3);
pins.spiFrequency(1000000);
pins.digitalWritePin(DigitalPin.P0, 0);
let command = pins.spiWrite(143);
let whoami = pins.spiWrite(0);
pins.digitalWritePin(DigitalPin.P0, 1);
basic.showNumber(whoami);
serial.writeLine("WHOAMI register value: " + whoami)
```

## 참고 항목

[SPI](https://developer.mbed.org/handbook/SPI)