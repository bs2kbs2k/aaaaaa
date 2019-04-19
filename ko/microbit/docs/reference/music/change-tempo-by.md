# 빠르기(bpm) 변경

[빠르기(bpm)](/reference/music/tempo) (음악이 연주되는 속도) 를 원하는 만큼 더 빠르게/느리게 합니다.

## 시뮬레이터

이 함수는 @boardname@ 보드와 일부 웹브라우저에서 동작합니다.

```sig
music.changeTempoBy(20)
```

## 매개 변수

* `빠르기(bpm)`. 빠르기를 변화시킬 bpm(beats per minute) [수(정수)](/types/number).(bmp 은 @boardname@ 보드를 이용해 소리를 출력할 때, 분당 비트 수를 의미합니다.)

## 예시

다음 코드는 음악을 12 bpm 더 빠르게 출력하도록 만듭니다.

```blocks
music.changeTempoBy(12)
```

다음 코드는 음악을 12 bpm *더 느리게* 출력하도록 만듭니다.

```blocks
music.changeTempoBy(-12)
```

## 참고 항목

[소리 출력](/reference/music/play-tone), [소리 출력(Hz)](/reference/music/ring-tone)