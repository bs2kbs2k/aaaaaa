# 시리얼통신 정수 전송

원하는 정수 값을 [시리얼통신](/device/serial) 포트로 전송합니다.

```sig
serial.writeNumber(0);
```

## 매개 변수

* `값`. 시리얼통신 포트로 전달시킬 [정수](/types/number)

## Example: one two three

This program repeatedly writes a 3-digit number to the serial port.

```blocks
basic.forever(() => {
    serial.writeNumber(123);
    basic.pause(5000);
});
```

## 예시: LED 그래프 데이터 시리얼 전송

`LED 그래프` 함수를 사용하면, 화면에 출력하는 동시에 시리얼통신 포트에도 같은 정수 값을 전송합니다.

```blocks
basic.forever(() => {
    led.plotBarGraph(input.lightLevel(), 255)
    basic.pause(10000);
})
```

## 참고 항목

[serial](/device/serial), [serial write line](/reference/serial/write-line), [serial write value](/reference/serial/write-value), [serial write numbers](/reference/serial/write-numbers)