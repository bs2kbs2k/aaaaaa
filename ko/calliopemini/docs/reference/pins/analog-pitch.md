# PWM 출력

Emits a Pulse With Modulation (PWM) signal to the current pitch [pin](/device/pins). Use [analog set pitch pin](/reference/pins/analog-set-pitch-pin) to set the current pitch pin.

```sig
pins.analogPitch(440, 300)
```

### 매개 변수

* `frequency` : [Number](/reference/types/number)
* `ms`: [Number](/reference/types/number)

### 예시

```blocks
pins.analogSetPitchPin("P0")
let frequency1 = 440
let duration = 1000
pins.analogPitch(frequency1, duration)
```

### 일반적인 음계의 진동수

* 440 = A4 : 440Hz = 피아노 건반 음계 라(A4)
* 더 자세한 정보는 [피아노 건반 음계 진동수](https://en.wikipedia.org/wiki/Piano_key_frequencies) 를 살펴보세요.

### 참고 항목

[@boardname@ 핀](/device/pins), [아날로그 PWM 설정](/reference/pins/analog-set-period), [아날로그 출력 설정](/reference/pins/analog-set-pitch-pin)