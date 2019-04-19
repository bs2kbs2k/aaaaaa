# 자기력

방향에 따른 자기력(자석이 당기는 힘) 크기를 측정해보세요.

```sig
input.magneticForce(Dimension.X);
```

## ~hint

@boardname@ 는 **마이크로 테슬라** 단위로 자기력을 측정할 수 있습니다.

## ~

### 매개 변수

* `기준 방향`. @boardname@ 가 놓여있는 공간에서 자기력을 측정할 방향: `x축 방향` (좌-우), `y축 방향` (앞-뒤 방향), `z축 방향` (위-아래)

### 리턴값

* a [number](/reference/types/number) of microteslas that means the strength of the magnet

### 예시: 금속 탐지기

다음은 자기력이 강해지면 @boardname@ 가운데 LED가 밝아지고, 자기력이 약해지면 가운데 LED가 어두어지도록 만든 예시 코드입니다.

```blocks
led.plot(2, 2)
basic.forever(() => {
    let f = input.magneticForce(Dimension.X)
    led.setBrightness(f / 2000)
})
```

### 참고 항목

[compass heading](/reference/input/compass-heading)