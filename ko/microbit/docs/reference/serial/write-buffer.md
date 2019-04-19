# write Buffer

버퍼에 들어있는 내용을 [시리얼통신](/device/serial) 포트로 전송합니다.

```sig
serial.writeBuffer(pins.createBuffer(0));
```

You place your data characters into an existing buffer. All of the data, the length of the buffer, is written to the serial port.

## 매개 변수

* **buffer**: a [buffer](/types/buffer) to write to the serial port.

## 예시

Read some characters of data from a device connected to the I2C pins. Write the data to the serial port.

```blocks
pins.i2cWriteNumber(132, NumberFormat.UInt8LE, 0);
let i2cBuffer = pins.i2cReadBuffer(132, 16, false);
serial.writeBuffer(i2cBuffer);
```

## 참고 항목

[read buffer](/reference/serial/read-buffer)