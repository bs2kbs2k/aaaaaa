# 라디오 신호 강도 수신

> 참고: 이 API는 더 이상 사용되지 않습니다! 대신 [라디오 데이터 수신하면 실행](/reference/radio/on-data-packet-received) 을 사용하세요.

`라디오(radio)` 신호 세기를 알아냅니다. `-128` 부터 `-42` 사이의 값을 가집니다. (`-128` 은 신호가 약한 것을 의미하며, `-42` 는 강한 신호를 의미합니다.)

@boardname@ 는 [라디오 데이터 수신하면 실행](/reference/radio/on-data-packet-received) 함수를 통해 마지막에 받은 데이터에서 신호 세기를 알아냅니다. **라디오 정수 수신** 이 먼저 실행되어야 합니다.

```sig
radio.receivedSignalStrength();
```

## 리턴값

* [수(정수)](/types/number). 신호 수신 강도. `-128` 부터 `-42` 사이의 정수 값.

## 시뮬레이터

이 함수는 @boardname@ 에서만 정상적으로 동작하고, 웹브라우저에서는 동작하지 않습니다.

## 예시

다음은 [빛 센서](/reference/radio/send-number) 에서 전달된 빛 센서값을 통해, 라디오 신호의 세기를 알아내는 예시입니다.

```blocks
let x = 0;
radio.setGroup(99);
basic.forever(() => {
    x = radio.receiveNumber();
    basic.showNumber(radio.receivedSignalStrength());
});
```

## 참고 항목

[라디오 데이터 수신하면 실행](/reference/radio/on-data-packet-received), [라디오 값 전송](/reference/radio/send-number), [시리얼통신 문자 받으면 실행](/reference/radio/on-data-received)

```package
radio
```