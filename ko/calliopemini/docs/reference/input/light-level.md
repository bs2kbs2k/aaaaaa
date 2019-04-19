# LED 스크린 빛 센서 밝기

주변의 빛 밝기(밝고 어두운 정도)를 측정해보세요. 빛 센서 밝기 값 `0` 은 어둠을 의미하고, `255` 가장 밝은 값을 의미합니다. @boardname@ 는 주변 빛의 양을 [LED 스크린](/device/screen) 에 있는 LED 들을 이용해 측정합니다.

이 함수를 처음 사용하면, `0` 으로 측정될 것입니다. 그 다음에 주변 빛의 양을 측정할 것입니다. 왜냐하면, 처음에 빛 센서(빛의 양을 측정하는 부분)에 전원이 입력되어야 하기 때문입니다.

```sig
input.lightLevel();
```

### 리턴값

* a [Number](/reference/types/number) that means a light level from `0` (dark) to `255` (bright).

### 예시: 빛 센서 밝기 출력하기

다음 코드는 `B` 버튼을 눌렀을 때, [LED 스크린](/device/screen) 주변의 빛 양을 측정하는 예시입니다.

```blocks
input.onButtonPressed(Button.B, () => {
    let level = input.lightLevel()
    basic.showNumber(level)
})
```

### 예시: 빛 밝기 LED 그래프

다음 코드는 @boardname@ 에서 [LED 그래프](/reference/led/plot-bar-graph) 형태로 빛의 밝기를 그려주는 예시입니다. @boardname@ 를 들고 밝기가 다른 곳들을 이리저리 다녀보면, LED 그래프 형태로 빛의 밝기가 다르게 표시되어 나타나게 됩니다.

```blocks
basic.forever(() => {
    led.plotBarGraph(input.lightLevel(), 255)
})
```

### 참고 항목

[가속도 센서 값](/reference/input/acceleration), [자기(나침반) 센서 각도](/reference/input/compass-heading)