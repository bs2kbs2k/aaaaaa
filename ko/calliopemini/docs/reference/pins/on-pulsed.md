# 펄스 감지하면 실행

원하는 핀을 디지털 입력 모드로 바꾼 후, 그 핀으로 입력되는 펄스가 **High** 또는 **Low** (선택) 인지에 따라, 실행시킬 코드를 등록할 수 있습니다.

```sig
pins.onPulsed(DigitalPin.P0, PulseValue.High, () => { });
```

### 매개 변수

* `name`. 설정할 @boardname@ 핀 (`P0` 부터 `P20`)
* `pulse`. 실행시킬 펄스 상태 (**High** 또는 **Low**)

### 예시

다음은 `P2` 핀을 디지털 입력 모드로 설정한 후, `LOW` 문자열을 `P2` 핀의 펄스 신호가 low 일때 출력하도록 만든 예시 코드입니다.

```blocks
pins.onPulsed(DigitalPin.P2, PulseValue.Low, () => {
    basic.showString("LOW");
});
```

### 참고 항목

[서보 펄스 설정](/reference/pins/servo-set-pulse), [펄스 주기(µs)](/reference/pins/pulse-duration), [디지털 입력](/reference/pins/digital-read-pin)