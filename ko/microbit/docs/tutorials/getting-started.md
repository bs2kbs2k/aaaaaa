# 튜토리얼 따라해보기

## 단계 1

Welcome! Place the `||basic:show string||` block in the `||basic:on start||` slot. Replace the `"Hello"` text with your name. Did you see it scroll?

```blocks
basic.showString("Micro!")
```

## 단계 2

@boardname@ 와 컴퓨터를 USB 케이블로 연결하고 `|Download|` 를 누르세요. **@drivename@** 드라이브에 프로그램을 저장합니다. 이렇게 하면 여러분이 만든 프로그램 코드가 @boardname@ 에 업로드 됩니다!

## 단계 3

텍스트가 움직이지 않고 있습니다. `||basic:show string||` 블록을 `||input:on button pressed||` 블록 안에 붙여 넣어, **A** 버튼을 눌렀을 때 스크롤 되도록 해보세요.

```block
input.onButtonPressed(Button.A, () => {
    basic.showString("Micro!")
});
```

## 단계 4

`|Download|` 를 눌러 프로그램 코드를 저장하고 다시 업로드해서, **A** 버튼을 눌러 텍스트가 스크롤 되도록 해보세요.

## 단계 5

**B** 버튼을 눌렀을 때, 웃는 스마일리 아이콘이 출력되도록 블록을 배치시켜보세요.

### 

`B` 버튼으로 바꾸려면, 드롭다운 메뉴를 눌러 선택하면 됩니다!

```block
input.onButtonPressed(Button.B, () => {
    basic.showLeds(`
    # # . # #
    # # . # #
    . . . . .
    # . . . #
    . # # # .
    `)
})
```

## 단계 6

`||basic:show number||` 블록과 `||Math:pick random||` 블록을 `||input:on shake||` 블록 안쪽에 붙여 넣은 후, 주사위를 굴려 수를 뽑는 것처럼 만들어보세요.

### 

@boardname@ 를 흔들면, `0` ~ `6` 범위에서 랜덤 수가 뽑혀, 스크린 화면에 나타날 것입니다.

```block
input.onGesture(Gesture.Shake, () => {
    basic.showNumber(Math.random(7))
})
```

## 단계 7

참 잘했습니다! 첫 번째 마이크로소프트 MakeCode 활동을 완료했습니다.