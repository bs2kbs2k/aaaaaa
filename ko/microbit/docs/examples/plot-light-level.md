# 빛 센서값 출력

Show the current light level as a bar graph.

```blocks
basic.forever(() => {
    led.plotBarGraph(
        input.lightLevel(),
        255
    )
})
```