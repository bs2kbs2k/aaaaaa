# 소리 출력

@boardname@ 의 `P0` 핀을 통해, 원하는 음을 원하는 시간 만큼 출력합니다.

## 시뮬레이터

이 함수는 @boardname@ 와 일부 웹브라우저에서만 정상적으로 동작합니다.

```sig
music.playTone(440, 120)
```

### 매개 변수

* `frequency` is the [number](/reference/types/number) of Hertz (how high or low the tone is).
* `ms` is the [number](/reference/types/number) of milliseconds that the tone lasts

## 예시

다음 예시는 도(C) 음의 진동수 값을 `freq` 변수에 저장하는 예시입니다. 그 다음에, 그 음을 1000 밀리초(1 초) 동안 출력합니다.

```blocks
let freq = music.noteFrequency(Note.C)
music.playTone(freq, 1000)
```

### 참고 항목

[지속 시간(ms)](/reference/music/rest), [소리 출력(Hz)](/reference/music/ring-tone) , [현재 빠르기(bpm)](/reference/music/tempo), [빠르기(bpm) 설정](/reference/music/set-tempo), [빠르기(bpm) 변경](/reference/music/change-tempo-by)