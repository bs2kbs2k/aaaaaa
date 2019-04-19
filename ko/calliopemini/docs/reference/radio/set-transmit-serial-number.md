# 라디오 시리얼 번호 전송 설정

`라디오(radio)` 데이터 패킷에, 데이터를 전송하는 보드의 시리얼 번호를 함께 포함시키도록 설정합니다.

```sig
radio.setTransmitSerialNumber(true);
```

### 매개 변수

* `transmit` is a [boolean](/reference/types/boolean) that represents whether the serial number needs to be transmitted.

### 예시

다음은 `라디오(radio)` 기능을 통해 전송하는 각 패킷에, 시리얼 번호를 함께 전송하는 예시입니다.

```blocks
radio.setTransmitSerialNumber(true);
```

### 참고 항목

[라디오 데이터 수신하면 실행](/reference/radio/on-data-packet-received), [라디오 정수 전송](/reference/radio/send-number), [라디오 값 전송](/reference/radio/send-value), [라디오 문자열 전송](/reference/radio/send-string)

```package
라디오
```