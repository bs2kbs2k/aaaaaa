# 시리얼통신 한 줄 전송

[시리얼통신](/device/serial) 포트로 문자열을 전송한 후, 줄 바꿈 구분 문자 `\r\n` 를 전송합니다.

```sig
serial.writeLine("");
```

### 매개 변수

* `text` is the [string](/reference/types/string) to write to the serial port

### 예시: 간단한 시리얼통신

다음 코드는 시리얼통신 포트를 통해 `BOFFO` 단어를 반복적으로 전송합니다. 단어를 출력할 때마다 줄이 바뀌게 됩니다.

```blocks
basic.forever(() => {
    serial.writeLine("BOFFO");
    basic.pause(5000);
});
```

### 예시: 실시간 스트리밍 데이터 전송하기

다음 코드는 [자기(나침반) 북쪽](/reference/input/compass-heading) 방향을 감지하고, 그 방향을 시리얼통신 포트로 반복적으로 전송합니다.

```blocks
basic.forever(() => {
    let heading = input.compassHeading()
    if (heading < 45) {
        serial.writeLine("N");
    } else if (heading < 135) {
        serial.writeLine("E");
    }
    else if (heading < 225) {
        serial.writeLine("S");
    }
    else {
        serial.writeLine("W");
    }
})
```

### 참고 항목

[시리얼통신](/device/serial), [시리얼통신 정수 전송](/reference/serial/write-number), [시리얼통신 문자열 전송](/reference/serial/write-string), [시리얼통신 값 전송](/reference/serial/write-value)