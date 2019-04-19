# 맑음

Turn off all the pixel LEDs.

```sig
light.clear()

```

## 예시

Turn off all the pixels when button `A` is pressed.

```blocks
light.setAll(0x00ff00)
input.buttonA.onEvent(ButtonEvent.Click, () => {
    light.clear()
})
```

## 참고 항목

[`||set All||`](/reference/light/set-all)

```package
circuit-playground
```