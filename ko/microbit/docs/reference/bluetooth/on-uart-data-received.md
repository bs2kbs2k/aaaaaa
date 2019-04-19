# 블루투스 UART 문자 받으면 실행

Registers an event to be fired when one of the delimiter is matched.

```sig
bluetooth.onUartDataReceived(",", () => {})
```

## 매개 변수

* `구분 문자`. [문자열](/types/string) 을 구분하기 위해 사용한 기호.

## 예시

다음은 `,` 문자를 기준으로 값을 읽어오는 예시입니다.:

```blocks
bluetooth.onUartDataReceived(serial.delimiters(Delimiters.Comma), () => {
    basic.showString(serial.readUntil(serial.delimiters(Delimiters.Comma)))
})
```