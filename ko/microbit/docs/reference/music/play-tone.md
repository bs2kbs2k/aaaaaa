# 소리 출력

@boardname@ 의 `P0` 핀을 통해, 원하는 음을 원하는 시간 만큼 출력합니다.

## ~ hint

이 함수는 @boardname@ 보드와 일부 웹브라우저에서 동작합니다.

## ~

```sig
music.playTone(440, 120)
```

## 매개 변수

* `진동수`. 헤르츠(Hz) 단위의 [수(정수)](/types/number)(음의 높낮이).
* `밀리초`. 음이 지속될 시간을 나타내는 [수(정수)](/types/number) 밀리초(ms).

## 예시

다음 예시는 도(C) 음의 진동수 값을 `freq` 변수에 저장하는 예시입니다. 그 다음에, 그 음을 1000 밀리초(1 초) 동안 출력합니다.

```blocks
let freq = music.noteFrequency(Note.C)
music.playTone(freq, 1000)
```

## 다른 핀 사용하기

[PWM 출력 설정](/reference/pins/analog-set-pitch-pin) 을 이용하면, 소리를 출력하는 핀을 바꿀 수 있습니다.

```blocks
pins.analogSetPitchPin(AnalogPin.P1);
```

## 참고 항목

[지속 시간(ms)](/reference/music/rest), [소리 출력(Hz)](/reference/music/ring-tone) , [현재 빠르기(bpm)](/reference/music/tempo), [빠르기(bpm) 설정](/reference/music/set-tempo), [빠르기(bpm) 변경](/reference/music/change-tempo-by)