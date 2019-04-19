# SPI통신 전송

SPI 슬레이브로 데이터를 전송한 후, 응답된 값을 리턴합니다.

```sig
pins.spiWrite(0);
```

### 매개 변수

* `value`. SPI 슬레이브로 전송할 값

### 리턴값

* a [number](/reference/types/number) Response from the SPI slave

### 참고 항목

[SPI](https://developer.mbed.org/handbook/SPI)