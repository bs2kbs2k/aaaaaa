# 시리얼통신

시리얼통신 연결을 이용해 데이터를 읽고 씁니다.

```cards
serial.writeLine("");
serial.writeNumber(0);
serial.writeValue("x", 0);
serial.writeString("");
serial.writeNumbers([0]);
serial.readUntil(",");
serial.readLine();
serial.readString();
serial.onDataReceived(",", () => {})
```

## 고급

```cards
serial.redirect(SerialPin.P0, SerialPin.P0, BaudRate.BaudRate115200);
serial.redirectToUSB();
serial.writeBuffer(pins.createBuffer(0));
serial.readBuffer(64);
```

## 참고 항목

[writeLine](/reference/serial/write-line), [writeNumber](/reference/serial/write-number), [writeValue](/reference/serial/write-value), [writeString](/reference/serial/write-string), [writeNumbers](/reference/serial/write-numbers), [readUntil](/reference/serial/read-until), [readLine](/reference/serial/read-line), [readString](/reference/serial/read-string), [onDataReceived](/reference/serial/on-data-received), [redirect](/reference/serial/redirect), [writeBuffer](/reference/serial/write-buffer), [readBuffer](/reference/serial/read-buffer), [redirectToUSB](/reference/serial/redirect-to-usb)