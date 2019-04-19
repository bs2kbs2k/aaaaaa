# 시리얼통신 한 줄 읽기

Read a line of text from the serial port.

```sig
serial.readLine();
```

#### ~hint

이 함수는 한 줄의 문자열의 마지막에 캐리지리턴 문자인 `\r` 가 있다고 가정하고 처리합니다. 시리얼통신 터미널 프로그램에서, 문자열의 마지막에 `\r` 기호를 추가해 주지 않으면, 이 함수는 값을 리턴하지 못합니다.

#### ~

### 리턴값

* a [string](/reference/types/string) containing input from the serial port, such as a response typed by a user

### 예시

다음 코드는 사용자 이름 입력을 요청한 후, 입력된 이름을 사용해 환영 메시지를 출력합니다.

```blocks
basic.forever(() => {
    serial.writeLine("What is your name?");
    let answer = serial.readLine();
    serial.writeString("Hello,");
    serial.writeLine(answer);
});
```

### 참고 항목

[시리얼통신](/device/serial), [시리얼통신 한 줄 전송](/reference/serial/write-line), [시리얼통신 값 전송](/reference/serial/write-value)