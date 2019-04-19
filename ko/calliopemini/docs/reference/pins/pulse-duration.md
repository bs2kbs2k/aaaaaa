# 펄스 주기(µs)

입력되는 펄스의 주기를 마이크로초(µs) 단위로 알아냅니다.

이 함수는 **펄스 감지하면 실행** 블록에 의해서 호출되어야 합니다.

```sig
pins.pulseDuration();
```

### 리턴값

입력되는 펄스의 주기. 마이크로초(µs) 단위

### 예시

다음은 `P0` 핀으로 high 펄스가 입력되었을 때, 그 펄스의 주기를 LED 스크린에 출력하는 예시입니다.

```blocks
pins.onPulsed(DigitalPin.P0, PulseValue.High, () => {
    basic.showNumber(pins.pulseDuration());
});
```

### 참고 항목

[서보 펄스 설정](/reference/pins/servo-set-pulse), [펄스 감지하면 실행](/reference/pins/on-pulsed), [디지털 입력](/reference/pins/digital-read-pin)