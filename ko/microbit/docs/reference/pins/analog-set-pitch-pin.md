# 아날로그 출력 설정

소리를 출력할 수 있도록 [핀](/device/pins) (P0, P1, P2) 을 설정합니다.

```sig
pins.analogSetPitchPin(AnalogPin.P0)
```

## 매개 변수

* `name`. [문자열](/types/string); 핀 이름 ("P0", "P1", 또는 "P2")

## 예시

```blocks
pins.analogSetPitchPin(AnalogPin.P0)
let frequency = 440
let duration = 1000
pins.analogPitch(frequency, duration)
```

## 일반적인 음계의 진동수

* 440 = A4 : 440Hz = 피아노 건반 음계 라(A4)
* 더 자세한 정보는 [피아노 건반 음계 진동수](https://en.wikipedia.org/wiki/Piano_key_frequencies) 를 살펴보세요.

## 참고 항목

[@boardname@ 핀](/device/pins), [아날로그 PWM 설정](/reference/pins/analog-set-period), [PWM 출력](/reference/pins/analog-pitch)