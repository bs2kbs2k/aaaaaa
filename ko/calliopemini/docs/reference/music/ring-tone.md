# 소리 출력(Hz)

`P0` 핀을 통해 원하는 주파수(음의 높낮음)의 음을 출력합니다. 출력되는 음은 정지시키기 전까지 계속 출력될 것입니다.

## 시뮬레이터

이 함수는 @boardname@ 와 일부 웹브라우저에서만 정상적으로 동작합니다.

```sig
music.ringTone(440)
```

### 매개 변수

* `frequency` is a [number](/reference/types/number) that says how high-pitched or low-pitched the tone is. **Hz** (**헤르츠**) 는 진동수 또는 음의 높낮이 값을 의미합니다.

### 예시

다음 프로그램은 @boardname@ 의 **가속도 센서 가속도** 값을 검사합니다. @boardname@ 의 **가속도** 를 측정합니다. (가속도는 @boardname@ 가 움직이는 속도가 빨라지거나 느려지는, 속도 변화 값을 의미합니다.) 측정한 가속도 값을 소리로 바꾸어 출력합니다. @boardname@ 의 이동 속도가 계속 빨라지면 높은 음이 출력되고, 이동 속도가 계속 느려지면 낮은 음이 출력됩니다. 재미있습니다. -- 직접 해보세요!

```blocks
basic.forever(() => {
    music.ringTone(input.acceleration(Dimension.X))
})
```

### 참고 항목

[지속 시간(ms)](/reference/music/rest), [소리 출력](/reference/music/play-tone), [현재 빠르기(bpm)](/reference/music/tempo), [빠르기(bpm) 설정](/reference/music/set-tempo), [빠르기(bpm) 변경](/reference/music/change-tempo-by)