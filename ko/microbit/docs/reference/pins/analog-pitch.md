# PWM 출력

PWM(Pulse With Modulation) 신호를 `P0` 핀으로 출력합니다. [아날로그 출력 설정](/reference/pins/analog-set-pitch-pin) 을 이용해 PWM 신호를 출력할 핀을 설정할 수 있습니다.

```sig
pins.analogPitch(440, 300)
```

## 매개 변수

* `진동수(frequency)`. [수(정수)](/types/number)
* `밀리초(ms)`. [수(정수)](/types/number)

## 예시

```blocks
pins.analogSetPitchPin("P0")
let frequency1 = 440
let duration = 1000
pins.analogSetPitchPin(AnalogPin.P1);
pins.analogPitch(frequency1, duration)
```

## 일반적인 음계의 진동수

* 440 = A4 : 440Hz = 피아노 건반 음계 라(A4)
* 더 자세한 정보는 [피아노 건반 음계 진동수](https://en.wikipedia.org/wiki/Piano_key_frequencies) 를 살펴보세요.

## 참고 항목

[@boardname@ 핀](/device/pins), [아날로그 PWM 설정](/reference/pins/analog-set-period), [아날로그 출력 설정](/reference/pins/analog-set-pitch-pin)