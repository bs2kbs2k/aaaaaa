# 가속도 센서값 출력

Plot acceleration in the `x` dimension on the LEDs.

```blocks
basic.forever(() => {
    led.plotBarGraph(
        input.acceleration(Dimension.X),
        1023
    )
})
```