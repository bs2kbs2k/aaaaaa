# 핀 풀(pull) 설정

특정 핀의 전기적 풀(pull) 을 설정합니다.

많은 @boardname@ 들의 핀들은 *pull-ups* 상태를 설정할 수 있습니다. 예를 들어, 풀-업은 어떤 핀에 공급되는 전압을 높게 설정할 수 있습니다. (3.3 volts, `1` 은 [디지털 입력](/reference/pins/digital-read-pin) 사용시) 버튼 스위치의 한 쪽이 풀-업 설정된 `P0` (high) 에 연결되어있고 다른 한 쪽이 `GND` (0 volts) 에 연결되어있는 경우, 그 버튼을 누르는 경우에 `P0` 에 흐르는 전류의 전압이 0 volts 가 되면서 @boardname@ 에서 버튼 누름을 감지하게 됩니다.

```sig
pins.setPull(DigitalPin.P9, PinPullMode.PullDown);
```

### 매개 변수

* `name`. 설정할 @boardname@ 핀 (`P0` 부터 `P20`)
* `pull`. 핀에 설정할 풀(pull) (**down**, **up**, **none**)

### 예시

다음은 `P0` 핀의 풀(pull) 상태를 **up** (high) 으로 설정하는 예시입니다.

```blocks
pins.setPull(DigitalPin.P0, PinPullMode.PullUp);
```

### 참고 항목

[@boardname@ | mbed](https://developer.mbed.org/platforms/Microbit/)