# 우유 몬스터 무선 연결하기

## ~avatar avatar

다른 @boardname@ 를 이용해 우유 몬스터를 원격으로 조종해보세요.

## ~

## 활동 소요시간: ~30분

이 파트를 위해서는 2개의 @boardname@ 가 필요합니다. 라디오 기능을 사용해, 우유 몬스터를 다른 @boardname@ 로 조종할 수 있습니다. 아래의 코드를 우유 몬스터 로봇의 @boardname@ 와 다른 "컨트롤러" @boardname@ 에 업로드하세요. **A** 버튼을 누를 때마다, 우유팩 몬스터가 한 번씩 움직일 것입니다.

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