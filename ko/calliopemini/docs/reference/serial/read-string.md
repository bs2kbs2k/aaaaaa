# 시리얼통신 문자열 읽기

시리얼통신 수신 버퍼에 저장되어있는 값을 문자열 형태로 읽어옵니다.

```sig
serial.readString();
```

### 리턴값

* a [string](/reference/types/string) containing input from the serial port. Empty if no data available.

### 예시

다음 코드는 시리얼통신으로 전송된 문자열을 스크린 화면에 스크롤합니다.

```blocks
basic.forever(() => {
    basic.showString(serial.readString());
});
```

### 참고 항목

[시리얼통신](/device/serial), [시리얼통신 한 줄 전송](/reference/serial/write-line), [시리얼통신 값 전송](/reference/serial/write-value)