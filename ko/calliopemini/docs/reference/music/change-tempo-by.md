# 빠르기(bpm) 변경

[빠르기(bpm)](/reference/music/tempo) (음악이 연주되는 속도) 를 원하는 만큼 더 빠르게/느리게 합니다.

## 시뮬레이터

이 함수는 @boardname@ 와 일부 웹브라우저에서만 정상적으로 동작합니다.

```sig
music.changeTempoBy(20)
```

### 매개 변수

* `bpm` is a [number](/reference/types/number) that says how much to change the bpm (beats per minute, or number of beats in a minute of the music that the @boardname@ is playing).

### 예시

다음 코드는 음악을 12 bpm 더 빠르게 출력하도록 만듭니다.

```blocks
music.changeTempoBy(12)
```

다음 코드는 음악을 12 bpm *더 느리게* 출력하도록 만듭니다.

```blocks
music.changeTempoBy(-12)
```

### 참고 항목

[소리 출력](/reference/music/play-tone), [소리 출력(Hz)](/reference/music/ring-tone)