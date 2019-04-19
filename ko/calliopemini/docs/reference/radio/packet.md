# 패킷(packet)

라디오 기능을 통해 수신된 데이터 패킷.

## 속성

* `receivedNumber` - The [number](/reference/types/number) that was sent in this packet or `0` if this packet did not contain a number. [라디오 정수 전송](/reference/radio/send-number) 과 [라디오 값 전송](/reference/radio/send-value) 을 살펴보세요.
* `receivedString` - The [string](/reference/types/string) that was sent in this packet or the empty string if this packet did not contain a string. [라디오 문자열 전송](/reference/radio/send-string) 과 [라디오 값 전송](/reference/radio/send-value) 을 살펴보세요.
* `time` - 데이터 패킷을 전송할 때 함께 보낸 그 @boardname@ 의 시스템 시간.
* `serial` - 데이터 패킷을 전송할 때 함께 보낸 그 @boardname@ 의 시리얼번호, @boardname@ 시리얼번호가 포함되어있지 않은 경우 `0`.
* `signal` - 데이터패킷을 수신했을 때의 신호 수신 강도. `255` (약함) 부터 `0` (강함).

### 참고 항목

[라디오 데이터 수신하면 실행](/reference/radio/on-data-packet-received),

```package
라디오
```