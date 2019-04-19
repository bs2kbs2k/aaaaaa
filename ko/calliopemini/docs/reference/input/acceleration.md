# 가속도 센서 값

Get the acceleration value (milli g-force), in one of three specified dimensions.

@boardname@ 보드의 움직임과 이동에 따른 가속도(속도가 빨라지거나 느려지는 속도 변화 값) 크기를 측정해보세요.

```sig
input.acceleration(Dimension.X);
```

## ~hint

밀리g(**milli-g**) 단위로 가속도를 측정할 수 있습니다. 밀리g는 중력가속도 **g** 의 1/1000 단위입니다. **1g** 는 지구에서 어떤 물체가 중력의 힘을 받아 떨어질 때의 시간에 따른 속도변화(가속도)를 의미합니다.

## ~

### 매개 변수

* `dimension` means which direction you are checking for acceleration, either `Dimension.X` (left and right), `Dimension.Y` (forward and backward), or `Dimension.Z` (up and down)

### 리턴값

* a [number](/reference/types/number) that means the amount of acceleration. When the @boardname@ is lying flat on a surface with the screen pointing up, `x` is `0`, `y` is `0`, and `z` is `-1023`.

### 예시: LED 그래프

다음 코드는 @boardname@ 의 가속도를 LED 그래프로 출력해주는 예시입니다.

```blocks
basic.forever(() => {
    led.plotBarGraph(input.acceleration(Dimension.X), 1023)
})
```

### 참고 항목

[가속도 센서 감지 값 설정](/reference/input/set-accelerometer-range), [자기(나침반) 센서 각도](/reference/input/compass-heading), [LED 스크린 빛 센서 밝기](/reference/input/light-level)