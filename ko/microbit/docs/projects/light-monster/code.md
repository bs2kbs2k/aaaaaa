# 코드 만들기

## @description 빛 몬스터를 살아있는 것처럼 만드는 코드

## ~avatar avatar

빛이 감지되면 입을 여는 프로그램 코드를 추가해보세요.

## ~

## 활동 소요시간: ~30분

@boardname@ 의 빛센서 값에 비례해서 입을 벌리는 코드를 작성할 것입니다. 반복 실행 구조에 넣어, 빛 센서값을 계속해서 읽어들이고 `||pins:map||` 함수를 이용해 회전 각도로 변환합니다.

```blocks
basic.forever(() => {
    pins.servoWritePin(AnalogPin.P0, pins.map(
        input.lightLevel(),
        0,
        255,
        30,
        150
    ))
})
```

## ~button /projects/light-monster/connect

NEXT: 연결하기

## ~