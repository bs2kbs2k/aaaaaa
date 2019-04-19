# 서보 보정기

다음 코드를 사용하면, 서보 모터의 각을 원하는 각도로 움직일 수 있도록 보정할 수 있습니다. `A` 버튼을 누르면 회전 각도를 5 도 만큼 줄이고, `B` 버튼을 누르면 5 도 만큼 크게 해줍니다.

현재 서보 모터의 각도는, 반복적으로 스크린 화면에 출력됩니다.

```blocks
let angle = 90
input.onButtonPressed(Button.A, () => {
    angle -= Math.max(0, 5)
    pins.servoWritePin(AnalogPin.P0, angle)
    led.stopAnimation()
})
input.onButtonPressed(Button.B, () => {
    angle += Math.min(180, 5)
    pins.servoWritePin(AnalogPin.P0, angle)
    led.stopAnimation()
})
basic.forever(() => {
    basic.showNumber(angle)    
})
pins.servoWritePin(AnalogPin.P0, angle)
```