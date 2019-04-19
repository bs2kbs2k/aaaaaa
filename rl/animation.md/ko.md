# animation

Create a built-in pixel animation to use when an animation is shown.

```sig
light.animation(0)

```

You have several animations to choose from. Pick the one you want to use.

## 매개 변수

* **kind**: which animation to use: > * `comet`: a shooting burst of light > * `rainbow`: many colors pulsing around > * `sparkle`: bright lights flashing all over > * `running lights`: a sequence of lights moving > * `theater chase`: theater lights moving along > * `color wipe`: a wave of color

## 리턴값

* the built-in ***animation*** information used by an animation operation.

## 예시 #exsection

Show the `sparkle` aninmation for 2 seconds when the `A` button is pressed.

```blocks
input.buttonA.onEvent(ButtonEvent.Click, () => {
    light.showAnimation(light.animation(3), 2000)
})
```

## 참고 항목

[`||show animation||`](/reference/light/show-animation)

```package
circuit-playground
```