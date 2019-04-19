# 핀 입력(아날로그 모드)값 출력

아래와 같은 코드를 사용하면 `P0`, `P1`, `P2` 를 통해 입력되는 아날로그 값을 그래프 형태로 출력할 수 있습니다. `A` 버튼을 누르면, 그 값을 스크린에 스크롤 시켜줍니다.

```blocks
let reading = 0
basic.forever(() => {
    reading = pins.analogReadPin(AnalogPin.P0)
    led.plotBarGraph(
        reading,
        1023
    )
    if (input.buttonIsPressed(Button.A)) {
        basic.showNumber(reading)
    }
})
```