# 튜토리얼 따라해보기

### 단계 1 @fullscreen

Welcome, let's get started by making the on-board NeoPixel blink! Drag a `||set pixel color||` block from the `Pixel` drawer into the `||forever||` block.

Hint:

```blocks
forever(() => {
    pixel.setColor(PixelColors.Red)
})
```

### 단계 2

Next, drag another `||set pixel color||` block from the `Pixel` drawer, place it below the first block, and change the selected color. Click the Hint button if you need help!

```blocks
forever(() => {
    pixel.setColor(PixelColors.Red)
    pixel.setColor(PixelColors.Blue)
})
```

### 단계 3

Open the `Loops` drawer and drag a `||pause||` block between the two `||set pixel color||` blocks. Set its argument to `1000`.

```blocks
forever(() => {
    pixel.setColor(PixelColors.Red)
    pause(1000)
    pixel.setColor(PixelColors.Blue)
})
```

### 단계 4

Open the `Loops` drawer and drag another `||pause||` below the two `||set pixel color||` blocks. Set its argument to `1000` as well.

```blocks
forever(() => {
    pixel.setColor(PixelColors.Red)
    pause(1000)
    pixel.setColor(PixelColors.Blue)
    pause(1000)
})
```

### 단계 6

Awesome! Congratulations on completing your first challenge on the @boardname@.