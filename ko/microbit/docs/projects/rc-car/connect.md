# RC 자동차 해킹 무선 연결하기

## 단계 4: 원격 리모트 조종

https://youtu.be/XXesoUC0XBU

장난감 RC 자동차를 무선으로 조종하기 위해서, 다른 @boardname@ 와 라디오 통신 기능을 사용할 수 있습니다. 다른 @boardname@ 는 자동차를 가속하거나 방향을 바꾸도록 하는 명령들을 무선으로 전송할 수 있습니다.

```blocks-ignore
let steering = 0
let throttle = 0
radio.onDataPacketReceived( ({ receivedString: name, receivedNumber: value }) =>  {
    led.toggle(0, 0)
    if (name == "throttle") {
        if (value > 0) {
            kitronik.motorOn(kitronik.Motors.Motor1, kitronik.MotorDirection.Reverse, 100);
        } else if (value < 0) {
            kitronik.motorOn(kitronik.Motors.Motor1, kitronik.MotorDirection.Forward, 100);
        } else {
            kitronik.motorOff(kitronik.Motors.Motor1);
        }
    } else if (name == "steering") {
        if (value > 0) {
            kitronik.motorOn(kitronik.Motors.Motor2, kitronik.MotorDirection.Forward, 100);
        } else if (value < 0) {
            kitronik.motorOn(kitronik.Motors.Motor2, kitronik.MotorDirection.Reverse, 100);
        } else {
            kitronik.motorOff(kitronik.Motors.Motor2);
        }
    }
})
basic.forever(() => {
    throttle = 0
    if (input.buttonIsPressed(Button.A)) {
        throttle = 100
    } else if (input.buttonIsPressed(Button.B)) {
        throttle = -100
    }
    radio.sendValue("throttle", throttle)
    steering = 0
    if (input.acceleration(Dimension.X) < -512) {
        steering = -100
    } else if (input.acceleration(Dimension.X) > 512) {
        steering = 100
    }
    radio.sendValue("steering", steering)
})
radio.setGroup(12)
```

```package
radio
pxt-kitronik-motor-driver=github:kitronikltd/pxt-kitronik-motor-driver#v0.0.3
```