# 소리 출력(멜로디)

@boardname@ 보드의 `P0` 핀을 통해 멜로디 음을 출력합니다.

## 시뮬레이터

이 함수는 @boardname@ 보드와 일부 웹브라우저에서 동작합니다.

```sig
music.beginMelody(music.builtInMelody(Melodies.Entertainer), MelodyOptions.Once)
```

또는 다음과 같은 포맷 : `NOTE[octave][:duration] eg: ['g5:1']`

```sig
music.beginMelody(['g4:1', 'c5', 'e', 'g:2', 'e:1', 'g:3'], MelodyOptions.Once)
```

## 매개 변수

* `멜로디`. 멜로디 표현을 위해 음과 박자를 저장한 배열.

## 예시

다음 예시는 미리 내장되어있는 `엔터테이너` 멜로디를 출력합니다.

```blocks
music.beginMelody(music.builtInMelody(Melodies.Entertainer), MelodyOptions.Once)
```

## 참고 항목

[소리 출력](/reference/music/play-tone), [지속 시간(ms)](/reference/music/rest), [소리 출력(Hz)](/reference/music/ring-tone) , [현재 빠르기(bpm)](/reference/music/tempo), [빠르기(bpm) 설정](/reference/music/set-tempo), [빠르기(bpm) 변경](/reference/music/change-tempo-by)