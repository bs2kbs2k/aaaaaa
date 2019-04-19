# 시리얼통신 문자 받으면 실행

> 참고: 이 API는 더 이상 사용되지 않습니다! 대신 [라디오 데이터 수신하면 실행](/reference/radio/on-data-packet-received) 을 사용하세요.

@boardname@ 가 [수(정수)](/types/number), [문자열(string)](/types/string) 을 `라디오(radio)` 를 통해 수신하는 경우에 따라, 원하는 프로그램 코드를 실행시킵니다.

```sig
radio.onDataReceived(() => { });
```

## 예시

다음은 @boardname@ 가 움직이는 가속도 값을, 라디오 기능을 이용해 계속해서 전송해주는 예시입니다. 또한, 근처에 있는 @boardname@ 에서 전송된 가속도 값을 수신해 보여줍니다. [LED 그래프](/reference/led/plot-bar-graph) 를 이용해, 값을 표현해 보여줍니다.

```blocks
basic.forever(() => {
    radio.sendNumber(input.acceleration(Dimension.X));
})
radio.onDataReceived(() => {
    led.plotBarGraph(radio.receiveNumber(), 1023);
})
```

## 참고 항목

[라디오 데이터 수신하면 실행](/reference/radio/on-data-packet-received), [라디오 값 전송](/reference/radio/send-number), [라디오 그룹 설정](/reference/radio/set-group)

```package
radio
```