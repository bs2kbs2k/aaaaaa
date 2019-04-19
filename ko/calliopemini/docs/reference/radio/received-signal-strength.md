# 라디오 신호 강도 수신

> 참고: 이 API는 더 이상 사용되지 않습니다! 대신 [라디오 데이터 수신하면 실행](/reference/radio/on-data-packet-received) 을 사용하세요.

Find how strong the `radio` signal is, from `255` to `0`. (`255` means a weak signal and `0` means a strong one.)

@boardname@ 는 [라디오 데이터 수신하면 실행](/reference/radio/on-data-packet-received) 함수를 통해 마지막에 받은 데이터에서 신호 세기를 알아냅니다. **라디오 정수 수신** 이 먼저 실행되어야 합니다.

```sig
radio.receivedSignalStrength();
```

### 리턴값

* a [number](/reference/types/number) between `255` and `0` that means how strong the signal is.

### 시뮬레이터

이 함수는 @boardname@ 에서만 정상적으로 동작하고, 웹브라우저에서는 동작하지 않습니다.

### 예시

다음은 [빛 센서](/reference/radio/send-number) 에서 전달된 빛 센서값을 통해, 라디오 신호의 세기를 알아내는 예시입니다.

```blocks
let x = 0;
radio.setGroup(99);
basic.forever(() => {
    x = radio.receiveNumber();
    basic.showNumber(radio.receivedSignalStrength());
});
```

### 참고 항목

[라디오 데이터 수신하면 실행](/reference/radio/on-data-packet-received), [라디오 값 전송](/reference/radio/send-number), [시리얼통신 문자 받으면 실행](/reference/radio/on-data-received)

```package
라디오
```