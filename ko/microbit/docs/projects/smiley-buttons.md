# 스마일리 버튼

## 단계 1

`||input:on button pressed||` 블록을 끌어온 후, **A** 버튼이 눌렸을 때 실행되도록 해보세요.

```blocks
input.onButtonPressed(Button.A, () => { 
});
```

## 단계 2

`||basic:show leds||` 블록을 `||input:on button pressed||` 블록의 안쪽에 넣어, 화면에서 스마일리 아이콘이 출력되도록 해보세요.

```blocks
input.onButtonPressed(Button.A, () => { 
    basic.showLeds(`
        # # . # #
        # # . # #
        . . . . .
        # . . . #
        . # # # .`
        );
});
```

## 단계 3

`|Download|` 를 눌러 @boardname@ 에 업로드 한 후, **A** 버튼을 눌러보세요.

## 단계 4

`||input:on button pressed||` 와 `||basic:show leds||` 블록들을 넣어 **B** 버튼을 눌렀을 때, 찡그린 얼굴 아이콘이 출력되도록 해보세요.

```blocks
input.onButtonPressed(Button.B, () => { 
    basic.showLeds(`
        # # . # #
        # # . # #
        . . . . .
        . # # # .
        # . . . #`
        );
});
```

## 단계 5

`|Download|` 를 눌러 @boardname@ 에 업로드 한 후, A 또는 B 버튼을 눌러보세요.

## 단계 6

`A` 와 `B` 버튼을 동시에 눌렀을 때의 비밀 모드를 추가해 보세요. 여러 개의 `||basic:show leds||` 블록들을 사용해 애니메이션을 만들어보세요.

```blocks
input.onButtonPressed(Button.AB, () => {
    basic.showLeds(`
        . . . . .
        # . # . .
        . . . . .
        # . . . #
        . # # # .
        `)
    basic.showLeds(`
        . . . . .
        . . # . #
        . . . . .
        # . . . #
        . # # # .
        `)    
})
```

## 단계 7

`|Download|` 를 눌러 @boardname@ 에 업로드 한 후, 친구들에게 보여주며 자랑해보세요!