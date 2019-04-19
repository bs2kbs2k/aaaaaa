# 깜박이는 하트

## 단계 1

`||basic:show leds||` 블록을 `||basic:on start||` 블록 안에 넣어 하트 모양을 그려보세요.

```blocks
basic.showLeds(`
    . # . # .
    # # # # #
    # # # # #
    . # # # .
    . . # . .`
    );
```

## 단계 2

Click `|Download|` to transfer your code into your @boardname@!

## 단계 3

하트 모양 아래에 또 다른 `||basic:show leds||` 블록을 붙여 넣어, 깜박이도록 만들어보세요.

```blocks
basic.showLeds(`
    . # . # .
    # # # # #
    # # # # #
    . # # # .
    . . # . .`);
basic.showLeds(`
    . # . # .
    # . # . #
    # . . . #
    . # . # .
    . . # . .`);
```

## 단계 4

블록들을 `||basic:forever||` 안에 넣어 애니메이션을 반복해서 출력하도록 만들어보세요.

```block
basic.forever(() => {
    basic.showLeds(`
        . # . # .
        # # # # #
        # # # # #
        . # # # .
        . . # . .`
        );
    basic.showLeds(`
        . # . # .
        # . # . #
        # . . . #
        . # . # .
        . . # . .`);
})
```

## 단계 5

`|Download|` 를 눌러 @boardname@ 에 업로드 한 후, 하트 모양이 깜박이는지를 확인해보세요!

## 단계 6

더 많은 `||basic:show leds||` 블록들을 이용해, 자신만의 애니메이션을 만들어보세요.

```blocks
basic.forever(() => {
    basic.showLeds(`
        . # . # .
        # # # # #
        # # # # #
        . # # # .
        . . # . .`
        );
    basic.showLeds(`
        . # . # .
        # . # . #
        # . . . #
        . # . # .
        . . # . .`);
    basic.showLeds(`
        . . . . .
        . # . # .
        . # # # .
        . . # . .
        . . . . .`);
})
```

## 단계 7

`|Download|` 를 눌러 프로그램 코드를 @boardname@ 에 업로드하세요.