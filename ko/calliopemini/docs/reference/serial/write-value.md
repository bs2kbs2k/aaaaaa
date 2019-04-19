# 시리얼통신 값 전송

변수 이름과 값을 쌍으로, 줄 바꿈 문자 조합(`\r\n`) 을 마지막에 삽입해 [시리얼통신](/device/serial) 포트를 통해 전달합니다.

```sig
serial.writeValue("x", 0);
```

### 매개 변수

* `name` is the [string](/reference/types/string) to write to the serial port
* `value` is the [number](/reference/types/number) to write to the serial port

### 예시: 실시간 스트리밍 데이터 전송하기

아래의 코드는, 10 초 마다 온도 센서값과 빛 센서값을 시리얼포트를 통해 전달합니다.

```blocks
basic.forever(() => {
    serial.writeValue("temp", input.temperature())
    serial.writeValue("light", input.lightLevel())
    basic.pause(10000);
})
```

#### ~hint

[값 전송](/reference/radio/send-value) 함수는 변수 이름을 의미하는 문자열과 수(값)를 쌍으로 묶어 전송합니다. 시리얼통신 포트를 통해 전송된 데이터들은 다른 @boardname@ 를 통해 수신이 가능하며, 수신한 데이터들을 `시리얼통신 값 전송` 을 이용해 시리얼통신 포트로 직접 전송할 수 있게 됩니다.

#### ~

### 참고 항목

[시리얼통신](/device/serial), [시리얼통신 한 줄 전송](/reference/serial/write-line), [시리얼통신 정수 전송](/reference/serial/write-number), [시리얼통신 값 전송](/reference/radio/send-value)