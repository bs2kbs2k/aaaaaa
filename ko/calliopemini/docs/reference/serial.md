# 시리얼통신

시리얼통신 연결을 통해 데이터를 읽어오고 출력합니다.

```cards
serial.writeLine("");
serial.writeNumber(0);
serial.writeValue("x", 0);
serial.writeString("");
serial.readUntil(",");
serial.readLine();
serial.readString();
serial.redirect(SerialPin.P0, SerialPin.P0, BaudRate.BaudRate115200);
serial.onDataReceived(",", () => {})
```

### 참고 항목

[writeLine](/reference/serial/write-line), [writeNumber](/reference/serial/write-number), [writeValue](/reference/serial/write-value), [writeString](/reference/serial/write-string), [readLine](/reference/serial/read-line), [redirect](/reference/serial/redirect-to)