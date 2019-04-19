# 코드 만들기

화분 흙의 습도가 낮아지면, 서보 모터를 움직여 물을 공급하도록 프로그램 코드를 만들어봅시다.

**[화분 흙 습도 측정](/projects/soil-moisture)** 프로젝트에서, 습도 센서를 통해 읽은 값 `reading` 이 대략 `500` 보다 작은 경우에, 수분이 부족하다는 것을 알았습니다. 센서로 읽은 값이 `reading < 500` 인 경우를 코드에 추가해, 건조한 경우로 판단할 수 있습니다.

```block
let reading = 0
if (reading < 500) { }
```

서보 모터가 **P2** 핀에 연결되어있기 때문에, `||pins:servo write||` 블록을 이용해서 서보 모터의 회전 각도를 바꿀 수 있습니다. 물이 없을 때까지 각도를 `0` 으로 유지하고, 물이 떨어지면 각도를 `80` 도로 바꿉니다.

```block
let reading = 0
if (reading < 500) {
    basic.showIcon(IconNames.Umbrella)
    pins.servoWritePin(AnalogPin.P2, 0);
    basic.pause(3000)
    pins.servoWritePin(AnalogPin.P2, 80)
    basic.pause(3000)
    pins.analogWritePin(AnalogPin.P2, 0)
}
```

위의 코드를 `||basic:forever||` 블록에 넣어야 하는데, [화분 흙 습도측정 코드](/projects/soil-moisture/connect) 에 있는 무한 반복 실행 블록 안으로 넣으면 됩니다.

```blocks
radio.setTransmitSerialNumber(true)
radio.setGroup(4)
led.setBrightness(64)
let reading = 0
basic.forever(() => {
    pins.analogWritePin(AnalogPin.P1, 1023)
    reading = pins.analogReadPin(AnalogPin.P0)
    radio.sendNumber(reading / 4);
    pins.analogWritePin(AnalogPin.P1, 0)
    led.plotBarGraph(
        reading,
        1023
    )
    if (input.buttonIsPressed(Button.A)) {
        basic.showNumber(reading)
    }
    if (reading < 500) {
        basic.showIcon(IconNames.Umbrella)
        pins.servoWritePin(AnalogPin.P2, 0);
        basic.pause(3000)
        pins.servoWritePin(AnalogPin.P2, 80)
        basic.pause(3000)
        pins.analogWritePin(AnalogPin.P2, 0)
    }
    basic.pause(5000);
})
```

자동으로 물을 주도록 만든 @boardname@ 물 공급기 동영상은 다음과 같습니다.

https://youtu.be/7eC_VjH1eP0

```package
radio
```