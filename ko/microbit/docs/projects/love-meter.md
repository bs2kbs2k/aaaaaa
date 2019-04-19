# Love Meter

사랑 측정기를 만들어보세요! @boardname@ 는 사랑을 느낍니다. 어떤 때는 많지 않게 느낍니다!

## 단계 1

**사랑 측정기** 장치를 만들어보세요. `||input:on pin pressed||` 블록을 이용해 `P0` 핀에 전기가 흐를 때 실행되도록 해보세요.

```blocks
input.onPinPressed(TouchPin.P0, () => {
});
```

## 단계 2

`||basic:show number||` 과 `||Math:pick random||` 블록을 사용해, `P0` 핀에 전기가 흐를 때 0 부터 100 까지 임의의 랜덤 값이 출력되도록 해보세요.

```blocks
input.onPinPressed(TouchPin.P0, () => {
    basic.showNumber(Math.random(101));
});
```

## 단계 3

@boardname@ 에 전원을 넣으면 `"LOVE METER"` 가 출력되도록 해보세요.

```blocks
basic.showString("LOVE METER");
input.onPinPressed(TouchPin.P0, () => {
    basic.showNumber(Math.random(101));
});
```

## 단계 4

`|Download|` 를 눌러 @boardname@ 에 프로그램을 업로드하세요. `GND` 핀을 한 손으로 잡고, 다른 손으로는 `P0` 핀을 잡아 프로그램을 실행시켜보세요.