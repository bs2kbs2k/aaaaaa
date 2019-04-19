# 우유 몬스터 코드 만들기

## @description 우유 몬스터를 살아있는 것처럼 만드는 코드

## ~avatar avatar

프로그램 코드를 추가해 우유 몬스터를 움직이게 만들어보세요.

## ~

## 활동 소요시간: ~30분

## 단계 1: 서보 모터 보정하기

우유 몬스터를 움직이기 위해서 @boardname@ 를 이용해, 서보 모터를 `0` 도부터 `180` 도까지 회전하도록 만들어야 합니다. 아래 코드에서: - `A` 버튼을 누르면 서보 모터를 180 도로 회전시키게 됩니다. (우유 몬스터의 입을 닫게 됩니다.) - `B` 버튼을 누르면 서보 모터를 0 도로 회전시키게 됩니다. (우유 몬스터의 입을 열게 됩니다.)

```blocks
input.onButtonPressed(Button.A, () => {
    pins.servoWritePin(AnalogPin.P0, 180)
    basic.showNumber(180)
})
input.onButtonPressed(Button.B, () => {
    pins.servoWritePin(AnalogPin.P0, 0)
    basic.showNumber(0)
})
basic.showString("calibrate")

```

## 단계 2: 회전 로터 붙이기

회전 로터를 **연결하기 전에** 서보 모터의 각도를 180 도로 이동시켜 두어야 합니다. 서보 모터의 각도가 180 도 일 때, 우유 몬스터의 입이 닫혀 있도록 하기 위해서입니다.

## ~ hint

스크류 드라이버를 이용해, 회전 로터를 서보 모터에 장착합니다.

## ~

https://youtu.be/YZfkMWTeH4o

## 단계 3: 서보 모터 보정 상태 확인하기

`A` 버튼을 누르면, 서보 모터에 연결된 회전 로터가 '윗' 방향으로 되어야 합니다.

https://youtu.be/bAqXEawUsSM

## 단계 4: 회전 로터에 끈 연결하기

우유 몬스터의 입이 **닫혀있는 상태** 에서, 서보 모터의 회전 축에 끈을 연결합니다.

https://youtu.be/AWsnwk_iA_A

## 단계 5: @boardname@ 에 케이블 연결하기

@boardname@ 와 서보 모터를 케이블들로 연결하고 배터리를 연결시킵니다.

https://youtu.be/fAR58GJUZdM

## 단계 6: 빛 센서 코드 만들기

@boardname@ 에 있는 빛 센서를 값을 이용해, 서보 모터가 움직이도록 프로그래밍 해보세요.

```blocks
basic.forever(() => {
    pins.servoWritePin(AnalogPin.P0, input.lightLevel())
    led.plotBarGraph(
        input.lightLevel(),
        0
    )
})
```

## 단계 6: 준비완료!

우유 몬스터가 준비되었습니다!

https://youtu.be/egl3fNAYylk   


## ~button /projects/milky-monster/connect

NEXT: 연결하기

## ~