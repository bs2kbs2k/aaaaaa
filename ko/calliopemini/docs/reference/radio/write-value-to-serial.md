# 시리얼 통신으로 값 출력

> 참고: 이 API는 더 이상 사용되지 않습니다! 대신 [라디오 수신 패킷을 시리얼로 전송](/reference/radio/write-received-packet-to-serial) 을 사용하세요.

`라디오(radio)` 를 통해 수신한 마지막 데이터 패킷을 JSON 포맷으로 시리얼 출력합니다.

```sig
radio.writeValueToSerial();
```

### 시리얼 통신 데이터 출력 형식

시리얼 통신으로 출력하는 데이터의 형식은 다음과 같습니다.:

- [send number](/reference/radio/send-number): ```{v:ValueSent,t:MicrobitTimeAlive,s:SerialNumber}```
- [send value](/reference/radio/send-value): ```{v:ValueSent,t:MicrobitTimeAlive,s:SerialNumber,n:"Name"}```
- [send string](/reference/radio/send-string): ```{t:MicrobitTimeAlive,s:SerialNumber,n:"Text"}```

### 예시

다음은 ```라디오``` 기능을 통해 데이터가 수신되었을 때( `A` 버튼이 두 번째 @boardname@ 에서 눌렸을 때), 시리얼 통신으로 온도 데이터를 전송합니다.

```blocks
input.onButtonPressed(Button.A, () => {
    radio.sendNumber(input.temperature());
});
radio.onDataReceived(() => {
    radio.writeValueToSerial();
});
```

다음은 `A` 버튼이 눌렸을 때, 시리얼 통신으로 데이터를 보내는 예시입니다.:

```Text
{v:27,t:323,s:0}
```

### 참고 항목

[라디오 정수 전송](/reference/radio/send-number), [라디오 값 전송](/reference/radio/send-value), [라디오 문자열 전송](/reference/radio/send-string), [라디오 데이터 수신하면 실행](/reference/radio/on-data-packet-received)

```package
라디오
```