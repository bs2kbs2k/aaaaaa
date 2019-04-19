# 우유팩 로봇 코드 만들기

## @description 우유팩 로봇을 살아있는 것처럼 만드는 코드

## ~avatar avatar

프로그램 코드를 추가해 우유팩 로봇을 움직이게 만들어보세요.

## ~

## 활동 소요시간: ~15분

## 단계 1: 서보 모터 연결하기

[서보 모터 101 설명서](/device/servo) 를 참고해서, @boardname@ 와 서보 모터를 연결시키세요.

https://youtu.be/m-HS8OyS0pw

## 단계 2: 빛 센서 코드 만들기

@boardname@ 에 있는 빛 센서를 값을 이용해, 서보 모터가 움직이도록 프로그래밍 해보세요.

```blocks
basic.forever(() => {
    led.plotBarGraph(
        input.lightLevel(),
        0
    )
    pins.servoWritePin(AnalogPin.P0, input.lightLevel())
})
```

https://youtu.be/Ah4fEbJtklU

서보 모터가 작동하는데, 아주 많이 움직일 수 있습니다. 서보 모터가 움직이는 범위를 보정해보세요.

## 단계 3: 서보 모터 보정하기

[서보 모터 보정 프로그램](/examples/servo-calibrator) 을 다운로드한 후, 로봇에 설치된 서보 모터가 움직여야 하는 최소 각도와 최대 각도를 찾아보세요.

https://youtu.be/lZxWC82HDn0

빛 센서로 읽어들인, 빛 센서 범위 `[0, 255]` 에 있는 값을, 서보 모터의 회전 각도 범위의 값 `[closed, opened]` 으로 매핑(변환) 시킬 것입니다. `pins.map` 을 사용합니다.

```blocks
let angle = 0
let closed = 0
let opened = 0
basic.forever(() => {
    led.plotBarGraph(
        input.lightLevel(),
        0
    )
    angle = pins.map(
        input.lightLevel(),
        0,
        255,
        opened,
        closed
    )
    pins.servoWritePin(AnalogPin.P0, angle)
})
// TODO: use the angle found at calibration!
opened = 95
// TODO: use the angle found at calibration!
closed = 175
```

## ~button /projects/milk-carton-robot/connect

NEXT: 연결하기

## ~