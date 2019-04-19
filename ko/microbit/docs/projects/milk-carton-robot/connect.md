# 우유팩 로봇 무선 연결하기

## ~avatar avatar

다른 @boardname@ 를 이용해 우유팩 로봇을 원격 조정해보세요

## ~

## 활동 소요시간: ~30분

이 파트를 위해서는 2개의 @boardname@ 가 필요합니다. 다른 @boardname@ 를 이용해 우유팩 로봇을 원격으로 조종해보세요. 아래의 코드를 우유팩 로봇의 @boardname@ 와 다른 "리모컨" @boardname@ 에 업로드하세요. `A` 버튼을 누를 때마다, 우유팩 몬스터가 한 번씩 이동할 것입니다.

```blocks
radio.onDataPacketReceived(({receivedNumber}) => {
    pins.servoWritePin(AnalogPin.P0, 0)
    basic.pause(500)
    pins.servoWritePin(AnalogPin.P0, 180)
    basic.pause(500)
})
input.onButtonPressed(Button.A, () => {
    radio.sendNumber(0)
})
```

```package
radio
```