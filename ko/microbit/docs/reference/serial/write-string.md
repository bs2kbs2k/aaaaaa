# 시리얼통신 문자열 전송

[시리얼통신](/device/serial) 포트를 통해 문자열을 전송합니다. 문자열 마지막에서 줄을 바꾸도록 하는 줄 바꿈 문자는 함께 전송하지 않습니다.

```sig
serial.writeString("");
```

## 매개 변수

* `텍스트`. 시리얼통신 포트로 전송시킬 [문자열](/types/string)

## 예시: 간단한 시리얼통신

다음 코드는 시리얼통신 포트를 통해 `JUMBO` 단어를 반복적으로 전송합니다. 단어를 출력하고 줄이 바뀌지는 않습니다.

```blocks
basic.forever(() => {
    serial.writeString("JUMBO");
    basic.pause(1000);
});
```

## 참고 항목

[시리얼통신](/device/serial), [시리얼통신 한 줄 전송](/reference/serial/write-line), [시리얼통신 정수 전송](/reference/serial/write-number), [시리얼통신 값 전송](/reference/serial/write-value)