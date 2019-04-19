# 라디오 데이터 수신하면 실행

Run part of a program when the @boardname@ receives a [number](/reference/types/number) or [string](/reference/types/string) over `radio`.

```sig
radio.onDataPacketReceived(({receivedNumber, receivedString, time, serial, signal}) => { });
```

### ~hint

원하는 패킷 데이터을 추가하거나 제거하려면, 톱니바퀴 모양을 누르면 됩니다.

### ~

### 콜백 매개 변수

* `패킷(packet)` - [패킷(packet)](/reference/radio/packet) . 라디오를 통해 수신된 패킷. 데이터 패킷에는 다음과 같은 속성값들을 포함시킬 수 있습니다. 
  * `receivedNumber` - The [number](/reference/types/number) that was sent in this packet or `0` if this packet did not contain a number. [라디오 정수 전송](/reference/radio/send-number) 과 [라디오 값 전송](/reference/radio/send-value) 을 살펴보세요.
  * `receivedString` - The [string](/reference/types/string) that was sent in this packet or the empty string if this packet did not contain a string. [라디오 문자열 전송](/reference/radio/send-string) 과 [라디오 값 전송](/reference/radio/send-value) 을 살펴보세요.
  * `time` - 데이터 패킷을 전송할 때 함께 보낸 그 @boardname@ 의 시스템 시간.
  * `serial` - 데이터 패킷을 전송할 때 함께 보낸 그 @boardname@ 의 시리얼번호, @boardname@ 시리얼번호가 포함되어있지 않은 경우 `0`.
  * `signal` - 데이터패킷을 수신했을 때의 신호 수신 강도. `255` (약함) 부터 `0` (강함).

### 예시

다음은 @boardname@ 가 움직이는 가속도 값을, 라디오 기능을 이용해 계속해서 전송해주는 예시입니다. 또한, 근처에 있는 @boardname@ 에서 전송된 가속도 값을 수신해 보여줍니다. [LED 그래프](/reference/led/plot-bar-graph) 를 이용해, 값을 표현해 보여줍니다.

```blocks
basic.forever(() => {
    radio.sendNumber(input.acceleration(Dimension.X));
})
radio.onDataPacketReceived(({ receivedNumber }) => {
    led.plotBarGraph(receivedNumber, 1023);
})
```

### 참고 항목

[라디오 정수 전송](/reference/radio/send-number), [라디오 문자열 전송](/reference/radio/send-string), [라디오 값 전송](/reference/radio/send-value), [라디오 그룹 설정](/reference/radio/set-group)

```package
라디오
```