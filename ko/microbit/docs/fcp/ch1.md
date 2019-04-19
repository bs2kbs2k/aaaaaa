# Chapter 1

여기에는 [Foundations of Computing and Programming: exploring the micro:bit](../fcp) Chapter 1 에 있는 코드 예시들이 있습니다. 각 예시들을 블록과 자바스크립트로 바꾸어 가며 실행시켜 볼 수 있고, 마이크로비트에 업로드 할 파일들도 찾아볼 수 있습니다.

## Figure 1.11

LED 스크린 코드:

```blocks
basic.showIcon(IconNames.Square)
led.plot(2, 2)
```

## Figure 1.12

버튼 A/B 눌리면 실행.

```blocks
input.onButtonPressed(Button.A, () => {
    basic.showIcon(IconNames.Square)
})
input.onButtonPressed(Button.B, () => {
    led.plot(2, 2)
})
```

## Figure 1.13

버튼 A/B 눌리거나, 흔들면 실행

```blocks
input.onButtonPressed(Button.A, () => {
    basic.showIcon(IconNames.Square)
})
input.onButtonPressed(Button.B, () => {
    led.plot(2, 2)
})
input.onGesture(Gesture.Shake, () => {
    basic.clearScreen()
}) 
```

## Figure 1.15

P0 핀으로 신호를 보내는 프로그램.

```blocks
basic.forever(() => {
    pins.digitalWritePin(DigitalPin.P0, 1)
    basic.pause(1000)
    pins.servoWritePin(AnalogPin.P0, 180)
    basic.pause(1000)
})
```

## Figure 1.17

라디오를 이용해 통신하기

```blocks
input.onButtonPressed(Button.A, () => {
    radio.sendString("A")
})
input.onButtonPressed(Button.B, () => {
    radio.sendString("B")
})
radio.onDataPacketReceived(({receivedString}) => {
    basic.showString(receivedString)
})
```