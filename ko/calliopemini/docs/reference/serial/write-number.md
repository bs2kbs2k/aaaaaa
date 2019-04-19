# 시리얼통신 정수 전송

원하는 정수 값을 [시리얼통신](/device/serial) 포트로 전송합니다.

```sig
serial.writeNumber(0);
```

### 매개 변수

* `value` is the [number](/reference/types/number) to write to the serial port

### 예시: 1부터 10까지

다음 코드는 10자리 정수값을 시리얼통신 포트를 통해 반복적으로 전송합니다.

```blocks
basic.forever(() => {
    serial.writeNumber(1234567890);
    basic.pause(5000);
});
```

### 예시: LED 그래프 데이터 시리얼 전송

`LED 그래프` 함수를 사용하면, 화면에 출력하는 동시에 시리얼통신 포트에도 같은 정수 값을 전송합니다.

```blocks
basic.forever(() => {
    led.plotBarGraph(input.lightLevel(), 255)
    basic.pause(10000);
})
```

### 참고 항목

[시리얼통신](/device/serial), [시리얼통신 한 줄 전송](/reference/serial/write-line), [시리얼통신 값 전송](/reference/serial/write-value)