# 패킷(packet)

라디오 기능을 통해 수신된 데이터 패킷.

## 속성

* `receivedNumber` - 패킷에 포함되어 전송된 [수(정수)](/types/number), 수(정수)가 포함되어있지 않은 경우 `0`. [라디오 정수 전송](/reference/radio/send-number) 과 [라디오 값 전송](/reference/radio/send-value) 을 살펴보세요.
* `receivedString` - 패킷에 포함되어 전송된 [문자열](/types/string), 문자열이 포함되어있지 않은 경우 빈 문자열. [라디오 문자열 전송](/reference/radio/send-string) 과 [라디오 값 전송](/reference/radio/send-value) 을 살펴보세요.
* `time` - 데이터 패킷을 전송할 때 함께 보낸 그 @boardname@ 의 시스템 시간.
* `serial` - 데이터 패킷을 전송할 때 함께 보낸 그 @boardname@ 의 시리얼번호, @boardname@ 시리얼번호가 포함되어있지 않은 경우 `0`.
* `signal` - How strong the radio signal is. The exact range of values varies, but it goes approximately from `-128` dB (weak) to `-42` dB (strong).

## 참고 항목

[라디오 데이터 수신하면 실행](/reference/radio/on-data-packet-received),

```package
radio
```