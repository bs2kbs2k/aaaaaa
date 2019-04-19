# Animations

## ~avatar avatar

Show different animations using the Neopixels on the @boardname@!

## ~

## 단계 1

Use `[light.showAnimationFrame(light.rainbowCycleAnimation())]` and make your code look like this:

```blocks
light.showAnimationFrame(light.rainbowCycleAnimation())
```

## 단계 2

Put a [while loop](/blocks/loops/while) around it, so it runs indefinitely.

```blocks
control.forever(() => {
    light.showAnimationFrame(light.rainbowCycleAnimation())
})
```

```sim
control.forever(() => {
    light.showAnimationFrame(light.rainbowCycleAnimation())
})
```

Try some of the other animations:

### Sparkle

```blocks
control.forever(() => {
    light.showAnimationFrame(light.sparkleAnimation())
})
```

### Color Wipe

```blocks
control.forever(() => {
    light.showAnimationFrame(light.colorWipeAnimation(light.colors(0xff0000)))
})
```

### Theatre Chase

```blocks
control.forever(() => {
    light.showAnimationFrame(light.theatreChaseAnimation())
})
```