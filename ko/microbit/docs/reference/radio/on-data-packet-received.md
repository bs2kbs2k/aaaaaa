# 라디오 데이터 수신하면 실행

@boardname@ 가 [수(정수)](/types/number), [문자열(string)](/types/string) 을 `라디오(radio)` 를 통해 수신하는 경우에 따라, 원하는 프로그램 코드를 실행시킵니다.

```sig
radio.onDataPacketReceived(({receivedNumber, receivedString, time, serial, signal}) => { });
```

## ~hint

원하는 패킷 데이터을 추가하거나 제거하려면, 톱니바퀴 모양을 누르면 됩니다.

## ~

## 콜백 매개 변수

* `패킷(packet)` - [패킷(packet)](/reference/radio/packet) . 라디오를 통해 수신된 패킷. 데이터 패킷에는 다음과 같은 속성값들을 포함시킬 수 있습니다. 
  * `receivedNumber` - 패킷에 포함되어 전송된 [수(정수)](/types/number), 수(정수)가 포함되어있지 않은 경우 `0`. [라디오 정수 전송](/reference/radio/send-number) 과 [라디오 값 전송](/reference/radio/send-value) 을 살펴보세요.
  * `receivedString` - 패킷에 포함되어 전송된 [문자열](/types/string), 문자열이 포함되어있지 않은 경우 빈 문자열. [라디오 문자열 전송](/reference/radio/send-string) 과 [라디오 값 전송](/reference/radio/send-value) 을 살펴보세요.
  * `time` - 데이터 패킷을 전송할 때 함께 보낸 그 @boardname@ 의 시스템 시간.
  * `serial` - 데이터 패킷을 전송할 때 함께 보낸 그 @boardname@ 의 시리얼번호, @boardname@ 시리얼번호가 포함되어있지 않은 경우 `0`.
  * `signal` - 데이터패킷을 수신했을 때의 신호 수신 강도. `-128` (약함) 부터 `-42` (강함).

## 예시

다음은 @boardname@ 가 움직이는 가속도 값을, 라디오 기능을 이용해 계속해서 전송해주는 예시입니다. 또한, 근처에 있는 @boardname@ 에서 전송된 가속도 값을 수신해 보여줍니다. [LED 그래프](/reference/led/plot-bar-graph) 를 이용해, 값을 표현해 보여줍니다.

```blocks
basic.forever(() => {
    radio.sendNumber(input.acceleration(Dimension.X));
})
radio.onDataPacketReceived(({ receivedNumber }) => {
    led.plotBarGraph(receivedNumber, 1023);
})
```

## 예시

다음은 떨어져 있는 두 대의 @boardname@ 사이에서 송수신되는, 데이터 패킷 수신 강도를 LED 그래프 형태로 출력해주는 예시입니다.

```blocks
basic.forever(() => {
    radio.sendNumber(0)
})
radio.onDataPacketReceived(({ signal, receivedNumber }) => {
    led.plotBarGraph(
        Math.abs(signal + 42),
        128 - 42
    )
})
```

## Troubleshooting

The on radio data event can only be created once, due to the hardware restrictions.

The radio set group might need to be set, synchronized , before the radio events will function.

## 참고 항목

[라디오 정수 전송](/reference/radio/send-number), [라디오 문자열 전송](/reference/radio/send-string), [라디오 값 전송](/reference/radio/send-value), [라디오 그룹 설정](/reference/radio/set-group)

```package
radio
```