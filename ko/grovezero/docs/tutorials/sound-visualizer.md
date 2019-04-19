# 사운드 비주얼라이저

## 소개 @fullscreen

Let's build a small pet that responds to your voice.

Follow the **Sound Visualizer** build instructions from the [Invention Guide](https://github.com/SeeedDocument/Bazzar_Attachment/raw/master/110060822/res/Grove%20Zero%20STEM%20Starter%20Kit%20Invention%20Guidance.pdf).

## 단계 1 @fullscreen

Drag a `||sensor:on loud sound||` block to the workspace.

```blocks
sensor.onLoudSound(function () {
})
```

## 단계 2 @fullscreen

Drag a `||display:LED matrix show leds||` block under the `||sensor:on loud sound||` and paint a cool drawing.

```blocks
sensor.onLoudSound(function () {
    display.showLeds(
    `
        # . . . #
        # . . . #
        . # . # .
        . . . . .
        . # # # .
        # . . . #
        `
    )
})
```

## 단계 3 @fullscreen

Click `|Download|` and follow the instructions to get your code onto your @boardname@. Try clapping, you should see your drawing!

## 단계 4 @fullscreen

Place one or more `||display:LED matrix show icon||` block under the first drawing and build your own animation.

```blocks
sensor.onLoudSound(function () {
    display.showLeds(
    `
        # . . . #
        # . . . #
        . # . # .
        . . . . .
        . # # # .
        # . . . #
        `
    )
    display.showIcon(IconType.Heart)
})
```

## 단계 5

Click `|Download|` and follow the instructions to get your code onto your @boardname@. Try clapping!