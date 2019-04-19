# 동전 던지기

## 단계 1

`||input:on button pressed||` 블록을 끌어온 후, **A** 버튼이 눌렸을 때 실행되도록 해보세요.

```blocks
input.onButtonPressed(Button.A, () => {
})
```

## 단계 2

**만약(if)** 블록을 넣고, `||Math:pick random true or false||` 블록으로 리턴되는 값을 체크하도록 해보세요.

`||Math:pick random true or false||` 블록은 `참(true)` 또는 `거짓(false)` 값을 랜덤으로 리턴합니다.

```blocks
input.onButtonPressed(Button.A, () => {
    if (Math.randomBoolean()) {
    } else {
    }
});
```

## 단계 3

`||basic:show icon||` 블록을 **만약(if)** 블록 안쪽에 넣고, 원하는 아이콘을 고르세요.

```blocks
input.onButtonPressed(Button.A, () => {
    if (Math.randomBoolean()) {
        basic.showIcon(IconNames.Skull)
    } else {
        basic.showIcon(IconNames.Square)
    }
});
```

## 단계 4

`|Download|` 를 눌러 @boardname@ 에 업로드 한 후, **A** 버튼을 눌러 확인해보세요.

## 단계 5

여러 개의 `||basic:show icon||` 블록들을 **만약(if)** 블록 윗쪽에 붙여, 동전 앞뒤가 반복적으로 뒤집히는 애니메이션을 만들어보세요.

```blocks
input.onButtonPressed(Button.A, () => {
    basic.showIcon(IconNames.Diamond)
    basic.showIcon(IconNames.SmallDiamond)
    basic.showIcon(IconNames.Diamond)
    basic.showIcon(IconNames.SmallDiamond)
    if (Math.randomBoolean()) {
        basic.showIcon(IconNames.Skull)
    } else {
        basic.showIcon(IconNames.Square)
    }
})
```

## 단계 6

`|Download|` 를 눌러 @boardname@ 에 업로드 한 후, **A** 버튼을 눌러 확인해보세요!