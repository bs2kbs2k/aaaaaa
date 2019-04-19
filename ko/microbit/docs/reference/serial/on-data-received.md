# 시리얼통신 문자 받으면 실행

Registers an event to be fired when one of the delimiter is matched.

```sig
serial.onDataReceived(",", () => {})
```

## 매개 변수

* `구분 문자`. [문자열](/types/string) 을 구분하기 위해 사용한 기호.

## 예시

다음은 `,` 문자를 기준으로 값을 읽어오는 예시입니다.:

```blocks
serial.onDataReceived(serial.delimiters(Delimiters.Comma), () => {
    basic.showString(serial.readUntil(serial.delimiters(Delimiters.Comma)))
})
```

## 참고 항목

[시리얼통신](/device/serial), [시리얼통신 한 줄 전송](/reference/serial/write-line), [시리얼통신 값 전송](/reference/serial/write-value)