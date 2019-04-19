# 랜덤 불(참/거짓) 값

`참(true)` 또는 `거짓(false)` 중에서 랜덤으로 뽑은 불 값을 리턴합니다.

```sig
Math.randomBoolean()
```

## 리턴값

* [불(참/거짓)](types/boolean). `참(true)` 또는 `거짓(false)` 중에서 랜덤으로 뽑은 값.

## 예시

@boardname@ 를 손에서 살짝 위로 던졌다 받았을 때, 동전 앞/뒤 맞추기처럼 되도록 만들어보세요. 마치 실제 동전을 던진 것처럼 LED 스크린에 'heads' / 'tails' 이 출력될 것입니다.

```blocks
input.onGesture(Gesture.FreeFall, () => {
    if (Math.randomBoolean()) {
        basic.showIcon(IconNames.Happy)
    } else {
        basic.showIcon(IconNames.Sword)
    }
})
```

## 참고 항목

[random](/reference/math/random)