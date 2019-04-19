# 지속 시간(ms)

`PO` 포트로 원하는 만큼의 일정 시간을 유지합니다. (다른 소리를 출력하지 않음)

## 시뮬레이터

이 함수는 @boardname@ 와 일부 웹브라우저에서만 정상적으로 동작합니다.

```sig
music.rest(400)
```

### 매개 변수

* `ms` is a [number](/reference/types/number) saying how many milliseconds the @boardname@ should rest. One second is 1000 milliseconds.

## 예시

```blocks
let frequency = music.noteFrequency(Note.C)
music.playTone(frequency, 1000)
music.rest(1000)
```

### 참고 항목

[소리 출력](/reference/music/play-tone), [소리 출력(Hz)](/reference/music/ring-tone), [현재 빠르기(bpm)](/reference/music/tempo), [빠르기(bpm) 설정](/reference/music/set-tempo), [빠르기(bpm) 변경](/reference/music/change-tempo-by)