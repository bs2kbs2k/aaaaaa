# 박자

음을 지속할 박자(시간). 밀리초(ms)

## 시뮬레이터

이 함수는 @boardname@ 보드와 일부 웹브라우저에서 동작합니다.

```sig
music.beat(BeatFraction.Whole)
```

## 매개 변수

* `박자`. 박자 수(온 음표, 16분 음표 등과 같은 박자) 

## 리턴값

* [수(정수)](/types/number). 박자를 출력할 밀리초 시간.

## 예시

```blocks
music.playTone(Note.C, music.beat(BeatFraction.Quarter))
```

## 참고 항목

[소리 출력](/reference/music/play-tone), [소리 출력(Hz)](/reference/music/ring-tone), [지속 시간(ms)](/reference/music/rest), [빠르기(bpm) 설정](/reference/music/set-tempo), [빠르기(bpm) 변경](/reference/music/change-tempo-by)