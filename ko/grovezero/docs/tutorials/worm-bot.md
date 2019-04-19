# 사운드 비주얼라이저

## 소개 @fullscreen

Build a **Worm Bot**, a cute companion that can change its face when you press a button.

Follow the **Worm Bot** build instructions from the [Invention Guide](https://github.com/SeeedDocument/Bazzar_Attachment/raw/master/110060822/res/Grove%20Zero%20STEM%20Starter%20Kit%20Invention%20Guidance.pdf).

![Worm bot circuit](/static/invention-guide/worm-bot/circuit.png)

## 단계 1 @fullscreen

Place a `||input:on button A click||` block in the code workspace.

```block
input.onButton(Button.A, ButtonEvent.Click, function () {
    display.showLeds(
    `
        . . . . .
        . # # # .
        . . . . .
        . . # . .
        # . . . #
        . # # # .
        `
    )
})
```

## 단계 2 @fullscreen

Place a `||display:show leds||` block under `||input:on button A click||`.

`||display:show leds||` will run when **A** is pressed on the Twin Button module.

```block
input.onButton(Button.A, ButtonEvent.Click, function () {
    display.showLeds(
    `
        . . . . .
        . # # # .
        . . . . .
        . . # . .
        # . . . #
        . # # # .
        `
    )
})
```

## 단계 3 @fullscreen

Click `|Download|` and follow the instructions to get your code onto your @boardname@. Press button **A**!

## 단계 4 @fullscreen

Place a `||input:on button B click||` block and `||display:show leds||` to display another image when **B** is pressed.

```block
input.onButton(Button.B, ButtonEvent.Click, function () {
    display.showLeds(
    `
        # # # # #
        # . # . #
        # # # # #
        . . # . .
        # . # . #
        . # . # .
        `
    )
})
```

## 단계 5 @fullscreen

Click `|Download|` and follow the instructions to get your code onto your @boardname@. Press button **A** or **B**!